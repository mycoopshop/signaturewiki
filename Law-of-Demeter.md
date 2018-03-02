Functions take no arguments
Each template is a standalone document
No string literals or global variables in functions
Methods and arguments are passed via templates
Template API converts them to instance variables

Example:
Instead of:
function foo(){
var injector = angular.injector(['ng', 'myModule']);
var greeter = injector.get('greeter');
}

do:
<foo class="angular" method="injector" arg="bar" cb="baz,bop">

with:
function foo(){
var modules = ['ng', 'myModule'];
console.log(foo.class);
}

and isolateScope and bindToController set to true.

**References**
http://www.xmlplease.com/xml/pi/
https://help.adobe.com/livedocs/coldfusion/7/htmldocs/wwhelp/wwhimpl/common/html/wwhelp.htm?context=ColdFusion_Documentation&file=00000998.htm
https://wiki.oasis-open.org/uiml/Practical_use_of_templates
https://stackoverflow.com/questions/8222757/assign-property-reference-in-javascript/22112086#22112086
https://medium.com/@evan.hopkins.us/the-law-of-demeter-and-its-application-to-react-ab1e054f13c5