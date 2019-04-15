To add a background-image rule via the CSSOM, first get a reference to the rules of the first stylesheet:

    var stylesheet = document.styleSheets[0].cssRules;

Then, get a reference to the end of the stylesheet:

    var end = stylesheet.length - 1;

Finally, insert a background-image rule for the body element at the end of the stylesheet:

    stylesheet.insertRule("body { background-image: url('http://cdn.sstatic.net/Sites/stackoverflow/img/favicon.ico'); }", end);

## Animation
* https://codepen.io/kh-mamun/pen/PWgzJe
* https://rosettacode.org/wiki/Animate_a_pendulum#JavaScript

## Set Theory
* https://css-tricks.com/logic-in-media-queries/
* https://www.w3.org/TR/mediaqueries-4/#evaluating
* https://www.sitepoint.com/css-selectors-level-4-the-path-to-css4/

## Real-Time Editing
* https://blog.frankmtaylor.com/2012/01/23/html5-contenteditable-and-css/
* https://css-tricks.com/show-and-edit-style-element/
* https://css-tricks.com/examples/EditableInvoice/
* https://developer.mozilla.org/en-US/docs/Web/CSS/:read-write
* https://webdesignerwall.com/tutorials/you-might-be-tempted-to-use-these-css-tricks-but-should-you

## References
* https://dxr.mozilla.org/mozilla-release/source/layout/style/res/html.css
* https://svn.webkit.org/repository/webkit/trunk/Source/WebCore/css/html.css
* https://src.chromium.org/viewvc/blink/trunk/Source/core/css/html.css
* http://csslint.net/
* https://developer.mozilla.org/en-US/docs/Web/CSS/grid
* https://robots.thoughtbot.com/css-animation-for-beginners
* https://news.ycombinator.com/item?id=14735269
* https://www.smashingmagazine.com/2011/09/the-guide-to-css-animation-principles-and-examples/
* https://codeburst.io/how-to-create-a-beautiful-animated-loader-with-nothing-but-css-d1962fc5a66c
* https://www.kirupa.com/html5/keyframes_and_the_animate_method.htm
* http://www.react.express/styling
* http://vanseodesign.com/css/custom-properties-and-javascript/
* https://www.triplet.fi/blog/practical-guide-to-react-and-css-modules/
* https://www.automationfuel.com/5-ways-to-style-react-components/
* https://modernizr.com/docs
* http://kizu.ru/en/blog/variable-order/