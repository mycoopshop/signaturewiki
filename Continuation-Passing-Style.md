Continuation-passing style. A function determines where to go next. It can decide to continue “as ordered” or to do something completely different. The following code is the CPS version of the previous example.

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