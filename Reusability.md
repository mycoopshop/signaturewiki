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
* 