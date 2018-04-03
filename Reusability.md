ES6 Template Literals:

      define(function(require) {

      var React   = require('react');
      var jsx     = require('lib/jsxquasi');

      var EchoComponent = React.createClass({
        getInitialState: function() {
            return { value: '' };
        },

        handleChange: function() {
            this.setState({ value: this.refs.input.getDOMNode().value });
        },

        render: function() {
            return jsx`
                <div>
                    <input 
                        ref='input' 
                        onChange='${this.handleChange}' 
                        defaultValue='${this.state.value}' />
                    ${this.state.value}
                </div>
            `;
        }
      })

      return function() {
        var comp = jsx`<${EchoComponent} />`;
        React.renderComponent(comp, document.body);
      };
    });



**References**
* https://medium.com/@gigobyte/enhancing-react-components-with-decorators-441320e8606a
* https://docs.angularjs.org/api/ng/directive/script
* https://www.ironin.it/blog/react-developers-may-like-vue.js-more.html
* https://github.com/facebook/react/issues/6436
* https://devhub.io/repos/mozilla-services-react-jsonschema-form
* http://bl.ocks.org/biovisualize/8187844
* https://marcysutton.github.io/react-a11y-presentation/#/
* http://www.24a11y.com/2017/reacts-accessibility-code-linter/
* https://reactjs.org/docs/composition-vs-inheritance.html
* https://joecritchley.svbtle.com/transclusion-in-react
* https://basarat.gitbooks.io/typescript/docs/template-strings.html
* https://blog.iansinnott.com/managing-state-and-controlled-form-fields-with-react/
* https://book.klipse.tech/how-to-create-interactive-reactjs-snippets.html
* https://medium.com/node-security/the-most-common-xss-vulnerability-in-react-js-applications-2bdffbcc1fa0
* https://v1.dhruvkumarjha.com/articles/building-a-static-website-using-react-js-part-2-creating-and-hosting-the-website
* http://voidcanvas.com/polymer-web-components-polyfills/
* http://blog.krawaller.se/posts/composition-in-cyclejs-choo-react-and-angular2/
* http://brewhouse.io/blog/2015/03/24/best-practices-for-component-state-in-reactjs.html
* http://buildwithreact.com/article/stateless-functional-components
* https://www.w3schools.com/bootstrap/bootstrap_ref_css_text.asp
* https://medium.com/@albertogasparin/forcing-state-reset-on-a-react-component-by-using-the-key-prop-14b36cd7448e