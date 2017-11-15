# Callbacks vs Events

Most of the major JavaScript libraries claim to support custom events in one form or another. For example, jQuery, YUI and Dojo all support a custom “document ready” event. However, the implementation of these custom events is always some form of callback system.

A callback system works by storing event handlers in an array. When the underlying event is detected the dispatch system loops through the array calling the callback functions in turn. So what’s wrong with that? Before I answer that, let’s look at some code.

Here is some simple code that uses the DOMContentLoaded event to perform two separate initialisations:

document.addEventListener("DOMContentLoaded", function() {
  console.log("Init: 1");
  DOES_NOT_EXIST++; // this will throw an error
}, false);

document.addEventListener("DOMContentLoaded", function() {
  console.log("Init: 2");
}, false);
What do you expect to see in the console when the document is loaded?

Well, you should see this (or something like it):

Init: 1

Error: DOES_NOT_EXIST is not defined

Init: 2
The point is, both functions are executed. You get an error in the first function but it does not stop the second function from executing.

The Problem

Now let’s look at some code based on a callback system. I’ll pick on jQuery because it’s the most popular:

$(document).ready(function() {
  console.log("Init: 1");
  DOES_NOT_EXIST++; // this will throw an error
});

$(document).ready(function() {
  console.log("Init: 2");
});
What do we see in the console?

Init: 1

Error: DOES_NOT_EXIST is not defined
The problem is clear. Callback systems are brittle. If any of the callback functions throw an error then the subsequent callbacks are not executed. In reality, this means that a poorly written plugin can prevent other plugins from initialising.

Dojo suffers exactly the same problem as jQuery. The YUI library takes a slightly different approach. It wraps a try/catch around its dispatch mechanism. The downside is that your errors occur silently:

YAHOO.util.Event.onDOMReady(function() {
  console.log("Init: 1");
  DOES_NOT_EXIST++; // this will throw an error
});

YAHOO.util.Event.onDOMReady(function() {
  console.log("Init: 2");
});
Produces:

Init: 1

Init: 2
Perfect initialisation! Nothing to worry about here! Except for the error that you don’t see.

So what’s the solution?

The Solution

The solution is to use a hybrid of a callback system and real event dispatch. We can trigger a fake event and from within that event, run the callback function. Each event handler has its own execution context. If an error occurs in our fake event then it won’t affect our callback system.

That sounds a bit complicated. I’ll illustrate with some code.

var currentHandler;

if (document.addEventListener) {
  document.addEventListener("fakeEvents", function() {
    // execute the callback
    currentHandler();
  }, false);

  var dispatchFakeEvent = function() {
    var fakeEvent = document.createEvent("UIEvents");
    fakeEvent.initEvent("fakeEvents", false, false);
    document.dispatchEvent(fakeEvent);
  };
} else { // MSIE

  // I'll show this code later
}

var onLoadHandlers = [];
function addOnLoad(handler) {
  onLoadHandlers.push(handler);
};

onload = function() {
  for (var i = 0; i < onLoadHandlers.length; i++) {
    currentHandler = onLoadHandlers[i];
    dispatchFakeEvent();
  }
};
Now we’ll use the code above to attach our two troublesome event handlers:

addOnLoad(function() {
  console.log("Init: 1");
  DOES_NOT_EXIST++; // this will throw an error
});

addOnLoad(function() {
  console.log("Init: 2");
});
OK. Let’s run the code above and see what we get:

Init: 1

Error: DOES_NOT_EXIST is not defined

Init: 2
Perfect! Just what we want. Both event handlers are executed and we also get a message telling us about the error in the first handler. Great!

But what about Internet Explorer I hear you ask (I have good hearing). MSIE does not support the standard event dispatch system. It has its own method; fireEvent but that only works with real events (e.g. click).

Rather than explain the solution in words, here is the code:

var currentHandler;

if (document.addEventListener) {

  // We've seen this code already

} else if (document.attachEvent) { // MSIE

  document.documentElement.fakeEvents = 0; // an expando property

  document.documentElement.attachEvent("onpropertychange", function(event) {
    if (event.propertyName == "fakeEvents") {
      // execute the callback
      currentHandler();
    }
  });

  dispatchFakeEvent = function(handler) {
    // fire the propertychange event
    document.documentElement.fakeEvents++;
  };
}
A similar approach except that we use the proprietary propertychange event as the trigger.

Summary

I’ve shown a very simple example of how to use the uderlying event system to fire custom events. Library authors should be capable of seeing how this can be extended to fully support cross-browser custom events.

Update

Some commenters have suggested using setTimeout. Here is my response to that:

For this particular example, a timer will work fine. This is just an example to illustrate the technique. The real usefulness of this is for other custom events. Most libraries implement custom events using a callback system. As I illustrated, callback systems are brittle. Dispatching events with timers will work to a degree but it is not how a real event system works. In a real system, events are dispatched sequentially. There are other concerns, like cancelling an event and stopping the event from bubbling. This would be impossible with timers.

https://developers.redhat.com/blog/2016/08/16/why-should-i-use-node-js-the-non-blocking-event-io-framework/
https://docs.mongodb.com/v3.0/faq/concurrency/
https://bjouhier.wordpress.com/2012/03/11/fibers-and-threads-in-node-js-what-for/
https://www.dunebook.com/how-to-increase-performance-of-nodejs-application/
https://nodeaddons.com/how-not-to-access-node-js-from-c-worker-threads/
https://blog.risingstack.com/concurrency-and-parallelism-understanding-i-o/
https://www.fpcomplete.com/blog/2016/12/concurrency-and-node