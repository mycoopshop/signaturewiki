Command decouples the object that invokes the operation from the one that knows how to perform it. It takes a function as a parameter and uses method dispatch based on the following naming convention: 
* All clients of Command objects treat each object as a "black box"
* The Command object's virtual execute() method is called whenever the client requires the object's "service".
* execute takes a parameter that maps to a concrete implementation
* Sequences of Command objects can be assembled into composite (or macro) commands.

The following example queues 24 processes and waits on each to finish before launching another.

    find /path -name '*.foo' | xargs -P 24 -I '{}' /cpu/bound/process '{}' -o '{}'.out


DOM0 Events are declarative events defined in the HTML and XHTML specifications as Intrinsic Events:

>Intrinsic events are attributes that are used in conjunction with elements that can have specific events occur when certain actions are performed by the user. The attributes indicated in the following table are added to the attribute set for their respective elements only when the modules defining those elements are selected.

>Certain elements of a markup language may have associated event handlers that are activated when certain events occur. User agents need to be able to identify those elements with event handlers statically associated (i.e., associated in the content, not in a script). In HTML 4 ([HTML4], section 18.2.3), intrinsic events are specified by the attributes beginning with the prefix "on": `onblur, onchange, onclick, ondblclick, onkeydown, onkeypress, onkeyup, onload, onmousedown, onmousemove, onmouseout, onmouseover, onmouseup, onreset, onselect, onsubmit, and onunload`.

>Internet Explorer has the correct scope for event handlers defined using the DOM Level 0 method of property assignment but not when using `attachEvent()`.

<pre>
 The Level 0 DOM supports the following nodeLists:

document.images[], which grants access to all images on the page.
document.forms[], which grants access to all forms on the page.
document.forms[].elements[], which grants access to all form fields in one form, whatever their tag name. This nodeList is unique to the Level 0 DOM; the W3C DOM does not have a similar construct.
document.links[], which grants access to all links (<a href>) on the page.
document.anchors[], which grants access to all anchors (<a name>) on the page.
</pre>

>The focus events defined in this specification occur in a set order relative to one another. The following is the typical sequence of events when a focus is shifted between elements (this order assumes that no element is initially focused):

<pre>

Event Name	Notes
1.	focusin	Sent before first target element receives focus
2.	focus	Sent after first target element receives focus
3.	focusout	Sent before first target element loses focus
4.	focusin	Sent before second target element receives focus
5.	blur	Sent after first target element loses focus
6.	focus	Sent after second target element receives focus
</pre>

>The following is the typical sequence of events when a focus is shifted between elements, including the deprecated DOMFocusIn and DOMFocusOut events. The order shown assumes that no element is initially focused.

<pre>
C.2.1 Legacy FocusEvent event order

Event Name	Notes
1.	focusin	Sent before first target element receives focus
2.	focus	Sent after first target element receives focus
3.	DOMFocusIn	If supported
4.	focusout	Sent before first target element loses focus
5.	focusin	Sent before second target element receives focus
6.	blur	Sent after first target element loses focus
7.	DOMFocusOut	If supported
8.	focus	Sent after second target element receives focus
9.	DOMFocusIn	If supported
</pre>


HTML Events are imperative events defined in the DOM specification as HTMLEvents:


<!-- begin snippet: js hide: false -->

<!-- language: lang-html -->

    <iframe src="https://www.w3.org/DOM/Graphics/dom2-map.svg" width="900" height="400"></iframe>
    <img src="https://www.w3.org/TR/DOM-Level-3-Events/images/eventflow.svg" width="400" height="400"/>

<!-- end snippet -->


**References**

* [XHTML Modularization: Intrinsic Events Module](https://www.w3.org/TR/xhtml-modularization/abstract_modules.html#s_intrinsiceventsmodule)

* [HTML Living Specification: Events - IDL Definitions](https://html.spec.whatwg.org/multipage/webappapis.html#idl-definitions)

* [DOM3 Events Semantic Requirements](https://www.w3.org/2008/webapps/wiki/DOM3_Events_Semantic_Requirements)

* [Techniques for User Agent Accessibility Guidelines 1.0, Section 3.11: Script and applet techniques - Script Techniques](https://www.w3.org/TR/UAAG10-TECHS/topics.html#scripts-applets)

* [UI Events Specification](https://www.w3.org/TR/DOM-Level-3-Events/)

* [Can Text Nodes Receive Events?](https://www.nczonline.net/blog/2008/02/09/can-text-nodes-receive-events/)

* [How to use the Level 0 DOM](http://www.quirksmode.org/js/dom0.html#use)

* [GitHub - Benvie/idl-for-javascript: IDL converted to a format and semantics usable by JavaScript](https://github.com/Benvie/idl-for-javascript)

* [GitHub - jsantell/chrome-api-definitions: Definition generator for Chrome Platform APIs](https://github.com/jsantell/chrome-api-definitions)

* [Open Mobile Alliance - Supporting Data](http://www.openmobilealliance.org/wp/supporting_data.html)

* [DOM handleEvent: a cross-platform standard since year 2000](https://medium.com/@WebReflection/dom-handleevent-a-cross-platform-standard-since-year-2000-5bf17287fd38)

* [IDL interface rules - Mozilla | MDN](https://developer.mozilla.org/en-US/docs/Mozilla/Developer_guide/Interface_development_guide/IDL_interface_rules)

* [From Scheme to Java: Section 1.9 The Command Pattern](https://www.cs.rice.edu/~cork/book/node53.html)

* [Unix Interface Design Patterns](https://homepage.cs.uri.edu/~thenry/resources/unix_art/ch11s06.html)