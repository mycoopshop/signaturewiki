Installing Jasmine standalone

Download the latest Jasmine release from the [Jasmine release page][1]: 


Running Jasmine locally

1. Run Jasmine in the browser by downloading the zip file, extracting it, the referencing the files as follows:

<pre>
<link rel="shortcut icon" type="image/png" href="jasmine/lib/jasmine-2.0.0/jasmine_favicon.png">

<link rel="stylesheet" type="text/css" href="jasmine/lib/jasmine-2.0.0/jasmine.css">

<script type="text/javascript" src="jasmine/lib/jasmine-2.0.0/jasmine.js"></script>

<script type="text/javascript" src="jasmine/lib/jasmine-2.0.0/jasmine-html.js"></script>

<script type="text/javascript" src="jasmine/lib/jasmine-2.0.0/boot.js"></script>
</pre>
     
Installing Jasmine using npm ([Node Package Manager][2])

1. Set up project directory for Jasmine
 
      Create a folder and run `npm init` this will create an empty `package.json` file and will ask some questions about your project to fill project `json` file.

   Add 2 directories `app` - for the Server and `spec` - for tests 

2. Get Jasmine

    From root project directory run  

    `npm install jasmine-node --save` 

    `npm install request --save`

    `npm install express --save`

    this will get you the packages 

    `./node_packages/.bin/jasmine-node spec` will run jasmine binary

    After this your `package.json` should look similar to this

   package.json file, after which that file should look like this:

  

      {
          "name": "Jasmine",
          "version": "0.0.1",
          "description": "Jasmine",
          "main": "index.js",
          "scripts": {
            "test": "./node_modules/.bin/jasmine-node spec"
          },
          "author": "Me",
          "license": "ISC"
        }



Install with npm

    npm install -g jasmine

If being used with karma, install `karma-jasmine`
    
    npm install --save-dev karma-jasmine


  [1]: https://github.com/jasmine/jasmine/releases

  [2]: https://www.npmjs.com/






<h2 style="clear:both;">METHODOLOGY</h2>
<div style="float:left;">
<b>BDD</b>
#   Before any coding starts, encapsulate each user behavior into a set of tests
#   Within each set, write a test against an object or method which represents a unit of business logic
#   Run the test. The test fails because there isn’t any code in place to support the code
#   Write some code to make the tests pass
#   Run the tests
#   Refactor the code
#   Test again and fix bugs and implementation
#   Reorganize or add new sets of tests as user behaviors are clarified
</div>

<div style="float:left;">
<b>TDD</b>                                                                  
#   Before any coding starts, write a test against an object or method which represents a unit of business logic
#   Run the test. The test fails because there isn’t any code in place to support the code.
#   Write some code to make the tests pass
#   Run the tests
#   Refactor the code
#   Test again and fix bugs and implementation
</div>

<div style="float:left;">
<b>QA Driven Unit Testing</b>                                                                  
#   Write some code
#   QA finds a bug
#   Write a test to make the code fail
#   Refactor the code
#   Run the test
</div>

<h2 style="clear:both;">SETUP</h2>
<div style="float:left;">
<b>Jasmine</b>                                                                  
# download the standalone distribution zip file                           
# edit an existing html file
# add jasmine.js, boot.js, and jasmine-html.js <script> tags
# add jasmine.css <link> tag
# add your source files as separate <script> tags
# add your spec files as separate <script> tags
# open the SpecRunner.html file to run your tests
# add source and spec <script> tags to add more tests
</div>

<div style="float:left">
<b>jQuery</b>
# download qunit.js and qunit.css
# edit an existing html file
# add #qunit and #qunit-fixture divs to a html file
# add qunit.js <script> tag
# add qunit.css <link> tag
# open the html file to run your tests
# use module() to add more tests
</div>

<h2 style="clear:both;">ARCHITECTURE</h2>
<div style="float:left;">
<b>Jasmine</b>                                                                  
# /test/lib/jasmine/jasmine.js
#    /test/lib/jasmine/jasmine.css
#    /test/lib/jasmine/jasmine-html.js
#    /test/lib/jasmine/boot.js
#    /test/src/foo.js
#    /test/spec/fooSpec.js
#    /test/SpecRunner.html
</div>

<div style="float:left;">
<b>QUnit</b>
#    /test/lib/qunit/qunit.css
#    /test/lib/qunit/qunit.js
#    /test/src/foo.js
#    /test/qunitrunner.html
</div>


<h2 style="clear:both;">Common Assertions</h2>
<div style="float:left;">
<b>Jasmine</b>
<pre>
toBeDefined
toBeTruthy
toBeFalsy
toThrow
toBe
toEqual
</pre>
</div>

<div style="float:left;">
<b>QUnit</b>
<pre>
ok
equal
notEqual
raises
deepEqual
strictEqual
</pre>
</div>

<div style="float:left;">
<b>Purpose</b>
<pre>
to test if something is not undefined
to test if two primitive values are equal
to test if two primitive values are not equal
to test if a callback throws an exception
to test if two objects are the same
to test if two primitive values are equal and the same type
</pre>
</div>


<h2 style="clear:both;">FEATURE COMPARISON</h2>
<div style="float:left;">
<b>Jasmine</b>
# Dependency injection via spies
## inject mock data from a call
## inject properties and functions
## overwrite a function for your test purposes
## fake AJAX
### andCallFake()
# custom assertions
## jasmine.addMatchers()
# Config API
## boot.js includes all public methods and global settings
# Logging API
## console.js includes logging methods
## console.log can be captured to emulate spy feature of Jasmine
# BDD assertions
## toMatch
## toBeDefined
## toBeUndefined
## toBeNull
## toContain
## toBeLessThan
## toBeGreaterThan
# Mock time
## jasmine.Clock.tick() can emulate time specific behaviors
# Type Assertions
## jasmine.any can emulate typeOf checks
# Spies
## spy can replace console.log to record method calls within a function
## spies can stub window method calls within a function
# Documentation
## The test file reads like documentation and describes everything the user can do
# Reporting
## jsApiReporter() receives a copy of spec results, and is used extract the data
</div>

<div style="float:left;">
<b>QUnit</b>
# Dependency injection via extend
## inject mock data from a call
# custom assertions
## QUnit.push( actual === expected, actual, expected, message );
# Config API
## JSON.stringify(QUnit.config) lists all configurable properties displayed on the toolbar
## QUnit.config.urlConfig.pop() removes each configurable property from the toolbar
## QUnit.init() is used for lazy load initialization of QUnit
## QUnit.config.reorder = false is used for showing tests in source order, not fail order
# Logging API
## QUnit.log = function log(details){console.log("Hi"+{"Actual":details.actual, "Expected":details.expected, "Source":details.source});}
# HTML fixtures 
## use #qunit-fixture to match the DOM tree your site actually contains
#DOM/JSON Data Dump
## QUnit.jsDump.parse() serializes DOM and JSON 
</div>

<h2 style="clear:both;">TRANSITION from console.log and global variables</h2>
<div style="float:left;">
<b>Traditional Development</b>
# Comments
# console.log
# window.location
# Date.now()
</div>

<div style="float:left;">
<b>TDD</b>                                                                  
# Behavior description
# spy
# stub
# mock Date
</div>


<h2 style="clear:both;">TEST FIRST DEVELOPMENT</h2>
<div style="float:left;">
<pre>

  module('foo', bar);

  function bar()
    {
    /* Move to before or setup step */
    var glob = "";
    var app = init(public_method);
    app.method = function(){
      /* move to spy */
      console.log(app.public_method());

      return app.public_method();
    }; 

     /* move to QUnit or Jasmine assert syntax equivalent */
    console.assert(app.method, true, "foo");

    /* Move to after or teardown step */
    app.on("destroy", function(){ var glob = app = undefined; })
    }
</pre>
</div>


<h2 style="clear:both;">TEST STRUCTURE</h2>
<div style="float:left;">
<b>Jasmine</b>
<pre>
describe('name',cb)

function pre()
  {
  myglobalvar = 'https://us.etrade.com';
  myglobalfn = Date();
  myglobalnamespace = mvstar;

  mvstar.init();  
  spyOn(mvstar, "public method");
  }

function post()
  {
  var myglobalvar = myglobalnamespace = myglobalfn = app = undefined;
  }

function cb()
  {
  beforeEach(pre);
  it('behavior', function()
    {
    app.method();
    expect(mvstar.init).toBeDefined();
    expect(mvstar.public_method).toHaveBeenCalled();
    }
  afterEach(post);
  }
</pre>
</div>

<div style="float:left;">
<b>QUnit</b>
<pre>
module('name',cb)

function pre()
  {
  var glob = ""
  var app = init();
  }

function post()
  {
  var glob = app = undefined;
  }

function cb()
  {
  setup(pre);
  test('behavior', function()
    {
    var foo = app.method();
    equal(foo, true);
    }
  teardown(post);
  }
</pre>

</div>

<h2 style="clear:both;">DEPENDENCY INJECTION IN TESTS VS CODE</h2>
* load the module
* inject a function pointer
* inject the controller/service and its dependencies into the function literal
* initialize the public properties
* call the public methods
* assert the boolean state of the return values (based on data type, equality, pattern, or truthiness)
* assert attempts to call methods of dependencies using spies
* replace session or network based data using mocks
* rerun using alternate public properties to access else branches
<div style="float:left;">
<b>Angular Mock</b>
<pre>
  myAppDev = angular.module('myAppDev', ['ngMockE2E']);
  test = angular.injector(['myAppDev']).get('$test');
  $httpBackend = angular.injector(['ngMock']).get('$httpBackend');
</pre>
</div>

<div style="float:left;">
<b>Angular Module</b>
<pre>
  myAppDev = angular.module('myAppDev');
  test = myAppDev.constant('test', ['$http',function($http){}]);
</pre>
</div>

<div style="clear:both;float:left;">
<b>Angular Mock</b>
<pre>
   module('trading');
    module('et.shared.neoServices');
    inject(snapshotServiceTest);
    
   function snapshotServiceTest(snapshotService)
      {
      var result = snapshotService;  
      expect(result).toBeDefined();
      expect(result.chartQuotes).toBeDefined();
      expect(result.chartURL).toBeDefined();
      expect(result.indexQuote).toBeDefined();
      expect(result.symbolQuote).toBeDefined();
      }
</pre>
</div>

<div style="float:left;">
<b>Angular Module</b>
<pre>
'use strict';

function snapshotService($q, $http, neoresource, $filter, chartFilter)
  {
  var api = {
    chartQuotes: chartQuotes,
    indexQuote: indexQuote,
    symbolQuote: symbolQuote,
    chartURL: chartURL
    };
  return api;
  }

angular.module('trading', ['et.shared.neoServices']) /* app.js */
angular.module('trading').factory('snapshotService', snapshotService);
</pre>
</div>

<h2 style="clear:both;">MODULAR TESTS</h2>
<div style="float:left;">
<b>Jasmine</b>                                                                  
<pre>
/*
describe() maps the plain English behavior to the test code

it() defines the user behavior and the implementation

beforeEach() adds dependencies into the global scope before the test

spyOn() acts as an interceptor to override method calls

toHaveBeenCalled() asserts whether the methods have executed

toHaveBeenCalledWith() asserts whether the method signature is correct

afterEach() removes dependencies from the global scope after the test

spyOn also acts as stub to replace host objects
 angular.module(['ng'], function($provide) { $provide.value('$window', {location: jasmine.createSpy('location') } ) } )
*/

describe("when a song is playing, we can toggle between play and pause", function() { 
    beforeEach(function() { 
        player.play(song); 
    }); 
    it("should pause the song", function() { 
        spyOn( player, "pause" ); // define the spy 
        player.togglePlay( song ); 
        expect( player.pause ).toHaveBeenCalled(); 
        expect( player.pause ).toHaveBeenCalledWith( ); 
        }); 
        it("should play the song", function() { 
            spyOn( player, "play" ); // define the spy 
            player.pause(); // just called here to set up our test to play the song next. 
            player.togglePlay( song ); 
            expect( player.play ).toHaveBeenCalled(); 
            expect( player.play ).toHaveBeenCalledWith( song ); 
         }); 
</pre>
</div>

<div style="float:left">
<b>QUnit</b>
<pre>
/*
module() groups tests into a namespace 

test() namespaces the test and its implementation

setup() adds dependencies into the global scope before the test

teardown() removes dependencies from the global scope after the test
*/

module("jQuery#enumerate");
 
test("chainable", 1, function() {
  var items = $("#qunit-fixture li");
  strictEqual(items.enumerate(), items, "should be chaninable");
});
 
test("no args passed", 3, function() {
  var items = $("#qunit-fixture li").enumerate();
  equal(items.eq(0).text(), "1. foo", "first item should have index 1");
  equal(items.eq(1).text(), "2. bar", "second item should have index 2");
  equal(items.eq(2).text(), "3. baz", "third item should have index 3");
});
 
test("0 passed", 3, function() {
  var items = $("#qunit-fixture li").enumerate(0);
  equal(items.eq(0).text(), "0. foo", "first item should have index 0");
  equal(items.eq(1).text(), "1. bar", "second item should have index 1");
  equal(items.eq(2).text(), "2. baz", "third item should have index 2");
});
 
</pre>
</div>

<h2 style="clear:both;">AJAX TESTING</h2>
<div style="float:left;">
<b>Jasmine</b>                                                                  
<pre>
/*
waits(time) stops code execution for a specified interval

runs(function) resumes execution at the end of the callback

waitsFor( function, msg, maxTimeOUt ) calls its function repeatedly until it returns true, so beware

expect() defines the comparison which should be true at the end
*/

//Simulates an async function by waiting until it has been called 50 times. 
var globalCounter = 0; 
var pingCounter = 0 
function returnAfterWait( ){ 
    pingCounter++; 
    if ( pingCounter == 50 ){ 
        globalCounter++; 
        return true; 
    }                         
}                             
describe('This is an async test', function(){ 
    //this test waits 500 ms before testing the results 
    it('should test async with timer', function(){ 
        var counter = 0; 
        runs( function(){ 
            setTimeout( function(){ counter++; }, 500 ); 
        }) 
        waits( 505 ); 
        runs( function(){ 
            expect(counter).toEqual( 1 ); 
        }) 
    }); 
    /* 
        This test waits to continue until 
        returnAfterWait() returns true 
    */ 
    it('should test async with a return', function(){ 
        var counter = 0; 
        waitsFor( function() { 
            return returnAfterWait(); },'this is the async message', 5000 ); 
        runs( function(){ expect(globalCounter).toEqual( 1 ); }) 
    }); 
});
</pre>
</div>

<div style="float:left">
<b>QUnit</b>
<pre>
/*
asyncTest() is a syntatic sugar forr Test( fn{stop()...start()} )

start() resumes execution at the end of the callback

expect() defines the number of assertions we should be triggered once start() is called
*/
    asyncTest("async3", function() {
        expect(1);
        $.getJSON("resource", function(result) {
            deepEqual(result, {
                status: "ok"
            });
            start();
        });
    });
</pre>
</div>

<h2 style="clear:both;">REFERENCES</h2>
<div style="float:left;">
[http://ditwebdev1w204m7.etrade.com/psweatte/qunit/qunit_builder.html QUnit Builder (Internal)]

[http://msdn.microsoft.com/en-us/magazine/gg490346.aspx BDD Primer]

[http://www.slideshare.net/tasanakorn/javascript-testdriven-development-tdd-with-qunit TDD with QUnit]

[http://benalman.com/talks/unit-testing-qunit.html Unit Testing with QUnit]

[https://www.adobe.com/devnet/html5/articles/unit-test-javascript-applications-with-jasmine.html Unit test JavaScript applications with Jasmine ]

[http://www.slideshare.net/larsthorup/advanced-jasmine Advanced Jasmine]

[http://stackoverflow.com/q/21766034/1113772 Jasmine with PhantomJS]

[http://www.devmynd.com/blog/2014-1-ember-js-testing-with-jasmine Ember.js Testing with Jasmine]

[https://gist.github.com/rjackson/6269405 Basic Ember.js Test Setup with QUnit]

[http://josephchapman.com/post/jasmine-mocks-and-spies/ Jasmine Mocks and Spies]

[http://pivotallabs.com/testing-javascript-promises/ Testing JavaScript Promises]

[http://www.slideshare.net/emwendelin/test-your-javascript Test your JavaScript]

[http://msdn.microsoft.com/en-us/library/hh404088.aspx Unit Testing Web Applications]

[https://github.com/larrymyers/jasmine-reporters Jasmine Reporters Plugin with JUnitXMLReporter]

[https://github.com/jquery/qunit-reporter-junit QUnit JUnit Reporter Plugin]

[https://github.com/devongovett/qunit-cli QUnit CLI NodeJS Plugin]

[https://github.com/gregjsmith/ng-demo-stack Ng Demo Stack:Angular + Browserify + QUnit + Sinon and Phantom]

[http://pivotallabs.com/jasmine-2-0-add-ons/ Jasmine 2.0 and Add-Ons]

[https://github.com/jquery/jquery-simulate jQuery Simulate]

</div>



**References**

* https://sites.google.com/site/unclebobconsultingllc/ant-jspc-and-other-horrors
https://ant.apache.org/manual/api/org/apache/tools/ant/taskdefs/optional/jsp/JspC.html

* https://ant.apache.org/manual/api/org/apache/tools/ant/taskdefs/optional/jsp/JspC.html

* https://stackoverflow.com/questions/2425721/unit-testing-datetime-now

* https://github.com/facebook/react/blob/94f44aeba72eacb04443974c2c6c91a050d61b1c/fixtures/dom/src/components/fixtures/date-inputs/index.js

* https://medium.com/@skidding/testing-react-components-30516bc6a1b3

* https://dev.to/elaziziyoussouf/tools-you-need-to-use-in-your-react-components-development--13a7

* https://github.com/tb/redux/tree/react-testing/examples/todomvc/src/components/__tests__