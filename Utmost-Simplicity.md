"To get portable data, you need to pick a representation that is usable in most programming languages"
"To get portable behavior, you need a maintainable program standard that runs on most computer systems"
"If something can be derived, store it as a function instead of a variable"
"There should be a single 'source of truth'"

## Simplest Controllers

1. RegExp
1. Excel Formulas
1. Recursion
1. RewriteRule
1. SetEnv/UnsetEnv/PassEnv
1. CSSOM
1. SMIL
1. toJSON
1. WPAD
1. XML Processing Instruction

## Simplest Stylesheets
* https://www.w3.org/StyleSheets/base.css

## Simplest REPLs
* https://jsfiddle.net/twophayse/ay6rkLwt/
* https://metacpan.org/release/Devel-REPL/source/lib/Devel/REPL.pm
* https://rosettacode.org/wiki/Interactive_programming#Tcl

## Simplest HTML
* http://dinosaur.compilertools.net/flex/manpage.html
* https://www.x.org/releases/X11R7.5/doc/man/man1/xman.1.html
* https://superevr.com/blog/2012/im-shocked-a-url-can-look-like-this/
* 209.59.119.34
* https://www.example.com
* https://www.internic.net/ 
* https://sqlite.org
* http://www.mobileread.mobi/
* http://wiki.c2.com/

## Simplest Specification
Hypertext Application Language (HAL) 
* http://stateless.co/hal_specification.html
* https://www.slideshare.net/kiphampton/magpie-13369038

## Simplest Event Model
* https://homepages.cwi.nl/~steven/xsltforms/
* https://homepages.cwi.nl/~steven/forms/examples/xmlcom/clock/clock4b.xhtml

## Simplest Domain Specific Language (DSL)

<pre>
Example Script: 
  create Vendor IBM
	 id 'IBM'
	 salesperson 'S1'
	 discount	10.0

  Translates Into:
	<script>
	 <create domain='Vendor', id='IBM'>
		<field name='id'>IBM</field>
		<field name='salesperson'>S1</field>
		<field name='discount'>10.0</field>
	 </create>
	</script>
</pre>

Simplest Message Passing

1. window.postMessage
1. Object.defineProperty
1. tunneling
    1. https://www.xml.com/pub/a/2004/03/24/tr.html
    1. https://www.w3schools.com/cssref/sel_target.asp
    1. https://www.gnu.org/software/gawk/manual/html_node/Variable-Scope.html
1. backreferences


Imperative

if (x == 7 && y == 7)

Declarative

select * from x, y
where num = 7

Interrogative

var num = new Map();
num.set({7:"x,y"}, num.foo)
num.get({7:"x,y"})

Imperative

if (num.hasOwnProperty(7)) { num.foo = Function; num.toJSON = num.foo }

Declarative

var num = {7:"x,y", toJSON: num.foo};

Interrogative

num.has(7) && num.has(toJSON) && num.size()

Imperative

Bring back real hiphop

Declarative

Hiphop is dead

Interrogative

Who killed hiphop?

Narrative

Back in the day...

Authoritative

Only God Can Judge Me

Imperative

Array.push/Array.pop/Array.sort/Array.join

Declarative

Array.concat/Array.from

Interrogative

Array.indexOf / Array.some / Array.every

Imperative

Set.add / Set.delete / Set.clear

Declarative

new Set()

Interrogative

Set.has / Set.size / 

Narrative

RegExp

Authoritatize

Object.defineProperty

WHO CAN COME AFTER HIM?

Variables - RegExp / XPath /xsl:variable (Every variable is a query result)
      $scope.href = function(){
        if(/1/.test($scope.template.name) === true)
          {return 'http://example.com';}
        else
          {return 'http://ietf.org';}
      };  

Templating - SSI/ESI

Data Binding - Excel / URI Templating

Theming - Image Maps / fonts / data:URIs

Debugging - Greasemonkey / eval

Coding - Emmet / JSLint / XHTML5

Documenting - Markdown

Visualizing - HTML5 Canvas 

# Annotations

https://9clouds.com/blog/14-slack-hacks-using/

https://www.infoworld.com/article/2946953/collaboration-software/hands-on-slack-gets-real-world-teamwork-test.html

https://get.slack.help/hc/en-us/articles/202288908-How-can-I-add-formatting-to-my-messages-

http://csis.pace.edu/~marchese/SE735/L1/L1.htm

# Requirements

https://www.sqlite.org/requirements.html

https://sqlite.org/fts5.html

# Spreadsheet-style programming

https://en.wikipedia.org/wiki/Datalog

https://sites.google.com/site/pydatalog/

# Game Architecture (Scoring, Interaction, Binding)

https://jsfiddle.net/twophayse/ay6rkLwt/

https://developer.apple.com/library/archive/samplecode/TicTacToe/Introduction/Intro.html#//apple_ref/doc/uid/DTS40010309

# Query Architecture 

https://anyonecanlearntocode.com/blog_posts/why-vue-not-react-is-the-new-jquery

https://www.quora.com/Why-did-jQuery-win

# Types
https://en.wikipedia.org/wiki/Rebol

# Names
https://en.wikipedia.org/wiki/Category:Computing_stubs
https://en.wikipedia.org/wiki/Wrapper_library

# Conditions
https://www.coderetreat.org/pages/facilitating/activity-catalog/
http://www.donhopkins.com/drupal/node/124
http://www.donhopkins.com/drupal/node/69

# State
http://etutorials.org/Macromedia/Fash+remoting.+the+definitive+guide/Part+III+Advanced+Flash+Remoting/Chapter+15.+Flash+Remoting+API/DataGlue+Object/
http://www.tomkitta.com/guides/flashMX2004.cfm
https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/mx/binding/utils/BindingUtils.html
https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/mx/rpc/remoting/RemoteObject.html
https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/mx/utils/ObjectProxy.html
https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/fl/data/DataProvider.html
https://www.adobe.com/devnet/flex/quickstarts/using_data_providers.html
https://jacksondunstan.com/articles/2439

# Game Creation
* [ActionScript for basic gaming](http://www.brandbyjosh.com/mediasite/p5_actionscript_gaming.pdf)
* [Real World Flash Game Development](https://doc.lagout.org/programmation/Actionscript%20-%20Flash%20-%20Flex%20-%20Air/Real-World%20Flash%20Game%20Development%202e%20-%20Griffith%20-%20Focal%20%282012%29.pdf)
* [Facilitating the Education of Game Development](https://www.gamasutra.com/features/20060510/20051104-final-thesis-nacke.pdf)

# Events
http://backbonejs.org/#Events-stopListening

https://medium.com/@interdigitizer/the-tricky-part-of-creating-an-mvc-with-jquery-4cc6ff88fe64

https://medium.com/@pitipatdop/little-neat-trick-to-capture-click-outside-react-component-5604830beb7f

https://medium.com/@pitipatdop/little-neat-trick-to-capture-click-outside-with-react-hook-ba77c37c7e82