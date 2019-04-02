    // Template Literals
    var box = jsx`
      <${Box}>
        ${
          shouldShowAnswer(user) ?
          jsx`<${Answer} value=${false}>no</${Answer}>` :
          jsx`
            <${Box.Comment}>
             Text Content
            </${Box.Comment}>
          `
        }
      </${Box}>
    `;



    // JSX
    var box =
      <Box>
        {
          shouldShowAnswer(user) ?
          <Answer value={false}>no</Answer> :
          <Box.Comment>
             Text Content
          </Box.Comment>
        }
      </Box>;

* Template Literals: https://facebook.github.io/jsx/
* Namespacing: http://2ality.com/2014/12/es6-symbols.html
* Tracing: http://2ality.com/2014/12/es6-proxies.html
* Type Coercion: http://2ality.com/2015/11/stage3-object-entries.html
* Overriding: http://2ality.com/2015/09/well-known-symbols-es6.html
* Overriding: http://2ality.com/2015/09/well-known-symbols-es6.html
* Unicode Escapes: http://2ality.com/2016/09/template-literal-revision.html
* Destructuring: http://2ality.com/2016/10/rest-spread-properties.html
* Iteration: http://2ality.com/2016/10/asynchronous-iteration.html
* Proper Tail-Calls: https://www.linkedin.com/pulse/tail-call-optimizations-es6-michael-clark
* Require=>Import: https://www.npmjs.com/package/replace-require-with-import
* RegExp Lookbehind Assertions: https://www.bram.us/2018/01/30/whats-new-in-ecmascript2018/
* Template Literal Revision: https://js.checkio.org/blog/ecmascript-2018/