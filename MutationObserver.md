    function bar(){console.log(Array.from(arguments))};
    var foo = new MutationObserver(bar);
    var baz = foo.observe(document.querySelector(".progress-segment.active"), { childList: true } );

**References**

* https://www.npmjs.com/package/react-mutation-observer
* https://eager.io/blog/three-real-world-use-cases-for-mutation-observer/
* https://bartsimons.me/detect-and-monitor-dom-changes-with-mutationobserver/
* https://davidwalsh.name/mutationobserver-api
* http://gists.fritzy.io/2014/01/29/mutation-observer-for-image-loaders/
* https://www.slideshare.net/nicjansma/measuring-the-performance-of-single-page-applications
* https://dejanstojanovic.net/javascript/2018/may/monitoring-dom-changes-with-javascript/
* https://codeburst.io/media-queries-based-on-element-width-with-mutationobserver-cf2eff172787
* https://building.lang.ai/hacking-with-dom-mutationobservers-348a50231580
* https://hackernoon.com/promise-based-detection-of-element-injection-94bc12e33966
* https://medium.com/all-technology-feeds/how-to-track-changes-in-the-dom-using-mutationobserver-583136df2328
* https://medium.com/dev-channel/after-mutationobserver-performanceobserver-and-intersectionobserver-we-have-another-observer-for-2c541bcb531b
* https://medium.com/@albertogasparin/getting-plain-text-from-user-input-on-a-contenteditable-element-b711aba2cb36
* https://medium.com/bunnyllc/vanilla-js-components-8d20c58b69f4
* https://medium.com/@gajus/making-the-anchor-links-work-in-spa-applications-618ba2c6954a
* https://hackernoon.com/easily-create-an-html-editor-with-designmode-and-contenteditable-7ed1c465d39b
* https://hackernoon.com/replacing-the-angular-1-router-with-elm-d71753e74e32
* https://medium.com/@heatherbooker/how-to-make-a-reusable-directive-in-vue-js-b28e1dfd76a3
* https://greatrexpectations.com/2017/01/05/cleaning-up-resources-using-mutationobserver/
* https://japhr.blogspot.com/2014/11/replacing-mutationobserver-with.html