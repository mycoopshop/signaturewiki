/*
Store this in the JS folder, then lazy load in via a bookmarklet
It will lazy load QUnit, then run itself
*/
function globals( assert ) {
      assert.ok(project_app_title, "project_app_title")
      assert.ok(rootURL, "rootURL")
      assert.ok(hashURL, "hashURL")
      assert.ok(category_url, "category_url")
      assert.ok(content_url, "content_url")
      assert.ok(preview, "preview");
      }

function nav(assert) {
 computedNav.assert = assert;
 $("a[href*='#/']").map(function(i, selector){computedNav(i, selector)});
 }

function computedNav(i, selector){
 var d = Date.now();
 $("a[href*='#/']")[i].click();
 location.hash = 'paused';
 QUnit.stop();
 setTimeout(function(){navStyles(selector)}, 3000)
 }

function navStyles(selector)
 {
 navStyles.selector = selector;
 QUnit.assert.ok(/rgb/.test(getComputedStyle(navStyles.selector).backgroundColor), String.concat(navStyles.selector.text, " has a background color of: ", getComputedStyle(navStyles.selector).backgroundColor));
 QUnit.assert.ok(/12px/.test(getComputedStyle(navStyles.selector).paddingTop), String.concat(navStyles.selector.text, " has a top padding of: ", getComputedStyle(navStyles.selector).paddingTop));
 QUnit.assert.ok(/12px/.test(getComputedStyle(navStyles.selector).paddingBottom), String.concat(navStyles.selector.text, " has a bottom padding of: ", getComputedStyle(navStyles.selector).paddingBottom));
 QUnit.assert.ok(/rgb/.test(getComputedStyle(navStyles.selector).color), String.concat(navStyles.selector.text, " has a color of: ", getComputedStyle(navStyles.selector).color));
 QUnit.assert.ok(getComputedStyle(navStyles.selector).fontWeight === "400", String().concat("font weight is: ", getComputedStyle(navStyles.selector).fontWeight));
 QUnit.assert.ok(/1[3-4]px/.test(getComputedStyle(navStyles.selector).fontSize), String().concat("font size is: ", getComputedStyle(navStyles.selector).fontSize )); 
 QUnit.assert.ok(/^Arial/.test(getComputedStyle(navStyles.selector).fontFamily), String().concat("font family is: ", getComputedStyle(navStyles.selector).fontFamily )); 
 QUnit.start()
 }

function left_rail()
 {
 QUnit.assert.ok($("#left_rail").css("width") === "200px", String().concat("Left rail width is: ", $("#left_rail").css("width")));
 }

function go()
  {      
  QUnit.start();
    test("Project specific Globals", globals);
    test("Left rail dimensions", left_rail);
    test("Check nav style properties", nav);
    test("Check default hash URL",function(assert){assert.ok(location.hash === "#/bond-basics"===true, "default URL is incorrect")});  
    test("Check for jQuery",function(assert){assert.ok(/function/.test(jQuery)===true, "jQuery is missing")})
    test("Check for JSON parser",function(assert){assert.ok(/function/.test(JSON["parse"])===true, "JSON parser is missing")})
    test("Check for form inputs",function(assert){assert.ok($("input").length > 0===true, "form inputs are missing")})
    test("Check for header tags",function(assert){assert.ok($("h1,h2").length > 1===true, "header tags (h1,h2) are missing")})
    test("Check for meta tags",function(assert){assert.ok($("meta").length > 0===true, "meta tags are missing")})
    test("Check for IE meta tag",function(assert){assert.ok($("meta[http-equiv='X-UA-Compatible']").length > 0=== true, "IE meta tag is missing")})
    test("Check for charset meta tag",function(assert){assert.ok($("meta[charset='utf-8'], meta[content='text/html; charset=utf-8']").length > 0 === true, "charset meta tag is missing(either HTML4 or HTML5 version is required)")})
    test("Check for doctype",function(assert){assert.ok(document.doctype.name === "html" === true, "doctype is missing")})
    test("Check for domain",function(assert){assert.ok(/etrade/.test(document.domain) ===true, "domain is no longer etrade.com")})
    test("Check for stylesheets",function(assert){assert.ok(document.styleSheets.length > 0===true, "stylesheets are inline")})
    test("Check for tag management",function(assert){assert.ok(window["tagmanagement"] === undefined === false, "tag management is missing")})
    test("Check for taskbar" ,function(assert){assert.ok($("script[src*='task']").length > 0 === false, "taskbar is loaded but not used")})
    test("Check for opinionlab" ,function(assert){assert.ok($("script[src*='oo_engine']").length > 0 === false, "opinionlab is loadded but not used")})
    test("Check for missing alt text" ,function(assert){assert.ok($("img:not[alt]").length > 0 === false, $("img:not[alt]").length)})
    test("Check for javascript: hrefs" ,function(assert){assert.ok($("a[href*='javascript']").length > 0 === false, $("a[href*='javascript']").length)})
    test("Check for empty hash(#) hrefs" ,function(assert){assert.ok($("a[href='#']").length > 0 === false, $("a[href='#']").length)})
  }
  
void(function foo()
  {      
  function runner()
    {
    QUnit.config.autostart = false;
    QUnit.init();
    go();
    }

  /* get body element */
  var body=document.body;
  var head=document.getElementsByTagName("head")[0];

  /* create script and link elements */
  var qUnitJS = document.createElement("script");
  var qUnitCSS = document.createElement("link");
  var qUnitDiv = document.createElement("div");
  
  /* link rel and type attributes required for lazy loading */
  qUnitCSS.rel="stylesheet";
  qUnitCSS.type="text/css";
  qUnitDiv.id="qunit";

  /* define script src attribute to lazy load */
  qUnitJS.src = "/skins/shared/js/test/qunit.js";

  /* append script and link elements */
  body.appendChild(qUnitDiv);
  body.appendChild(qUnitJS);
  head.appendChild(qUnitCSS);
  
  /* define link href after DOM insertion to lazy load */
  qUnitCSS.href="/skins/shared/css/test/qunit.css";

  /* call tests after QUnit loads */
  qUnitJS.onload = runner;
 
  }())