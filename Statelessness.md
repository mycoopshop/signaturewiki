## DOM based stateless toggling

1. Unique CSS class names can be date based. For example: 

    const ID = 'cls' + Date.now().toString();

2. Query selectors can target the class name for DOM mutation. For example:

    document.querySelector(event.target.className).parentNode.setAttribute('class', 'hidden');

3. The CSSOM can be updated to customize styling for the unique class name. For example:
    
    document.stylesheets[0].insertRule(ID + '{color: red}')

## References
* https://medium.com/dailyjs/high-performance-dynamic-styles-db28c873940
* http://jamesknelson.com/state-react-1-stateless-react-app/
* https://blog.cloudboost.io/react-functional-stateless-components-tutorial-example-fsc-147abc08f1?gi=726949919873
* https://www.zsoltnagy.eu/container-components-and-stateless-functional-components-in-react/
* https://www.jstwister.com/post/react-stateless-functional-components-best-practices/
* https://www.sitepoint.com/optimizing-react-performance-stateless-components/
* https://medium.com/@ethan_ikt/react-stateless-functional-component-with-typescript-ce5043466011
* https://hackernoon.com/react-stateless-functional-components-nine-wins-you-might-have-overlooked-997b0d933dbc?gi=80138541a906
* https://www.zsoltnagy.eu/container-components-and-stateless-functional-components-in-react/
* https://github.com/Microsoft/TypeScript/issues/8657
* https://medium.com/@mogon2990/infinite-routes-recursion-with-react-router-cdc6a4bb8e1d
* http://jsfiddle.net/cowboy/Ly3Luft4/
* https://kyleshevlin.com/loading-state-trick-for-stateless-functional-components-in-react/
* https://medium.com/@wwayne_me/how-to-manually-open-select-in-react-1169967eb33b
* https://reactjs.org/docs/forwarding-refs.html#displaying-a-custom-name-in-devtools
* https://stackoverflow.com/questions/41248130/stateless-component-a-valid-react-element-or-null-must-be-returned
* https://stackoverflow.com/questions/40412072/stateless-react-how-to-pass-key
* https://stackoverflow.com/questions/39135912/react-onkeydown-onkeyup-events-on-non-input-elements?rq=1
* https://stackoverflow.com/questions/38577224/focus-on-next-field-when-pressing-enter-react-js
* https://stackoverflow.com/questions/29321742/react-getting-a-component-from-a-dom-element-for-debugging/39165137#39165137
* https://news.ycombinator.com/item?id=11239738
* https://github.com/mobxjs/mobx/issues/48
* https://github.com/mobxjs/mobx-utils
* https://github.com/mobxjs/mobx/issues/681
* https://github.com/mobxjs/mobx-react/issues/471
* https://news.ycombinator.com/item?id=13151317
* https://hackernoon.com/the-fundamental-principles-behind-mobx-7a725f71f3e8
* https://stackoverflow.com/questions/41670725/react-ref-syntax-and-components-as-pure-functions
* https://stackoverflow.com/questions/47740017/manage-focus-on-stateless-components-react
* https://docs.bugsnag.com/platforms/browsers/react/#advanced-configuration
* https://stackoverflow.com/questions/48712345/react-props-id-binding-to-onclick-in-a-stateless-component
* https://hackernoon.com/becoming-fully-reactive-an-in-depth-explanation-of-mobservable-55995262a254?gi=35c582cb80a3


# Examples
* https://codepen.io/vitalyq/pen/oBvxJB?editors=0010
* https://jsfiddle.net/twophayse/32fye262/1/
* http://jsfiddle.net/ssorallen/4G46g/
* https://jsfiddle.net/gmsa/gfg30Lgv/
* https://jsfiddle.net/fJ9wq/

# Code
 
    /* You can, however, use the ref attribute inside a functional component as long as you refer to a DOM element or a class component:
    */
    function CustomTextInput(props) {
    // textInput must be declared here so the ref can refer to it
    let textInput = React.createRef();

    function handleClick() {
      textInput.current.focus();
    }

    return (
      <div>
        <input type="text" ref={textInput} />

        <input type="button" value="Focus the text input" onClick={handleClick}/>
      </div>
      );
    }