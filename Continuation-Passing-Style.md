>Continuation-passing style. A function determines where to go next. It can decide to continue “as ordered” or to do something completely different. The following code is the CPS version of the previous example.

    function f() {
        g(function (result) {
            console.log(result);
        });
    }
    function g(success) {
        h(success);
    }
    function h(success) {
        success(123);
    }

>But for our purposes, we understand partial application to be an operation that takes a polyadic function and applies some of the arguments and produces a function to be executed elsewhere and/or later. A fully generalized partial application operation permits us to apply one or more arguments in any position (possibly leaving holes to be filled), but let's consider the simplest of all possible partial applications: Given a polyadic function and a single value, it applies the value to the first argument and returns a function representing the rest of the application.

>Let's do it by hand. Working backwards, we want a function that looks like this:

    var heliosGreets = function (you) {
      var me = 'Helios';
  
      return greet(me, you)
    };

    heliosGreets('Eartha')
      //=> 'Hello, Eartha, my name is Helios'

>We can't have 'Helios' hard-coded, so we’ll hoist it out into an Immediately Invoked Function Expression:

    var heliosGreets = (function (me) {
      return function (you) {
        return greet(me, you)
      }
    })('Helios');

    heliosGreets('Eartha')
      //=> 'Hello, Eartha, my name is Helios'