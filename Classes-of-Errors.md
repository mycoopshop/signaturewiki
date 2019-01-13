Here are a few off the top of my head:

<pre>
Class                 Feature                             Example
Type Error            Single Data Type                    awk
Type Mismatch         Union Types                         XQuery
Reference Error       No Variables                        sed
Mismatched Braces     No Braces                           python
Dangling semicolon    Significant Whitespace              python
Buffer Overflow       No Pointer Arithmetic               Ada
Division by Zero      Default to infinity                 lua
Circular Reference    All values are immutable strings    tcl
Circular Import       No Cyclical Dependencies            OCaml
Ambiguous Type        Hindley-Milner type inference       OCaml
Not enough args       Partial Application                 Haxe
Import Error          Implicit Standard Library           Coldfusion
Leaky Abstraction     No Conditional Logic                CSS
Object Expected       Everything is an object             SmallTalk
No such method        Reification                         SmallTalk
Infinite Loop         No Side Effects                     DSSSL
Deadlock              Software Transaction Memory         Clojure
Namespace Conflict    Stack Save/Restore                  PostScript
Invalid arguments     Stack Machine                       PostScript
Heisenbug             Message Passing Concurrency         Erlang
</pre>


## References

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors
https://dzone.com/articles/top-10-javascript-errors-from-1000-projects-and-ho-1
https://blog.sentry.io/2017/09/28/react-16-error-boundaries
https://github.com/substack/tape/issues/59
https://thefullstack.xyz/debug-exceptions-react-native
https://blog.sentry.io/2017/09/28/react-16-error-boundaries
https://www.w3.org/TR/qaframe-spec/
https://www.w3.org/MarkUp/Test/HTML401/current/assertions/assertions_toc.html
https://www.infoq.com/news/2016/08/v8-ignition-javascript-inteprete
https://webkit.org/blog/3846/type-profiling-and-code-coverage-profiling-for-javascript/

## React
Events:https://github.com/facebook/react/blob/master/packages/react-dom/src/events/ReactBrowserEventEmitter.js
Plugins: https://github.com/facebook/react/blob/master/packages/react-dom/src/events/ChangeEventPlugin.js
Draconian Error Handling: https://github.com/facebook/react/issues/11846
Async Loading: https://github.com/facebook/react/issues/1739
Global Errors: https://github.com/facebook/react/issues/10474
Autocomplete: https://github.com/facebook/react/issues/1159
Interactive Validation: https://reactjs.org/docs/uncontrolled-components.html 
metadata: https://github.com/facebook/react/issues/1259
Async Rendering: https://github.com/facebook/react/issues/12227
focus/blur: https://github.com/facebook/react/issues/10380
IE/Edge: https://github.com/facebook/react/issues/3751
Keyboard Accessibility: https://github.com/facebook/react/issues/7024
Memoization: https://github.com/facebook/react/issues/7942
Prioritization: https://github.com/facebook/react/blob/master/packages/react-reconciler/src/__tests__/ReactIncrementalPerf-test.internal.js
Side-Effects: https://github.com/facebook/react/issues/9559
False-Positives: https://github.com/facebook/react/pull/8706
Emulating State Changes: http://reactkungfu.com/2016/03/dive-into-react-codebase-handling-state-changes/
Context Switching: https://reactarmory.com/guides/context-free-react-router
Cargo Culting: http://jamesknelson.com/push-state-vs-hash-based-routing-with-react-js/
Caching: https://github.com/facebook/react/blob/master/packages/simple-cache-provider/README.md
Pub/Sub: https://github.com/facebook/react/blob/master/packages/create-subscription/README.md
NodeJS: http://kangax.github.io/jstests/var-let-const/