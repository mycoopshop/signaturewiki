1 Measurement
1.1 Non-Project Time
1.2 Non-Development Project Time
2 Development
3 Rapid Prototyping
3.2 jtidy
3.3 jsFiddle
3.4 Debugging
3.5 Linting
3.6 Ten Minute Tasks
3.6.1 Test Mock Data
3.6.2 Sync Copy Deck Text
3.6.3 Adding ARIA
3.6.4 Fix Layout
3.6.5 Test Filters
3.6.6 Start App Server
3.6.7 Setup session
3.6.8 Update JIRA
3.6.9 Update QC
3.7 30 Minute Tasks
3.7.1 Parameterize code
3.7.2 Test Services
3.7.3 Add scripts to index.html
3.7.4 Test Controllers
3.7.5 Test XSLT
3.8 60 Minute Tasks
3.8.1 Trace Errors
3.8.2 Create Markup and Styles from Comps
3.8.3 Pixel Perfection
3.9 120 Minute Tasks
3.9.1 Generalize Code
3.9.2 Unit Test
3.9.3 Integration Testing
3.9.4 Functional Test
3.9.5 Isolation of Bugs
3.10 240 Minute Tasks
3.10.1 Diagram Flows
3.11 360 Minute Tasks
3.11.1 Refactor Code
3.12 480 Minute Tasks
3.12.1 Error Messaging
3.12.2 Rollback and Reapply after Code Freeze
3.13 Browser
3.14 IDE
3.14.1 HTML
3.14.2 JavaScript
3.14.3 CSS
3.15 Boilerplate
3.16 Pseudocode
3.17 Bootstrap 2
3.17.1 Fluid Rows (non-floated)
3.17.2 Inline-Block Form Fields
3.17.3 Block Form Fields
3.18 Bootstrap 3
3.18.1 No Float
3.18.2 Left aligned Block Row
3.18.3 Indented Row
3.18.4 Indented Column
3.18.5 Relative Containers
3.18.6 Inline-Block Containers
3.18.7 Inline-Table
3.18.8 Inline-Block Form Fieldset
3.18.9 Inline-Block Form Fields
3.18.10 100% Width Grid-Based Blocks
3.18.11 100% Width Grid-Based Inline-Blocks
3.18.12 Justified Inline-Blocks
3.18.13 Vertical Alignment
3.18.14 Centered Blocks:
3.18.15 25% width:
3.18.16 50% width:
3.18.17 75% width:
3.18.18 Block containers:
3.18.19 Help content:
3.18.20 Collapsing Margins:
3.18.21 No outline
3.18.22 Pseudo href
3.18.23 Tooltips
3.18.24 ARIA
3.18.25 Pressed
3.18.26 Hidden
3.18.27 Name Label
3.18.28 Modal Control Indicator
3.18.29 Tab Control Indicator
3.18.30 Modal Container
3.18.31 Modal Content
3.18.32 Screen Reader
3.18.33 Persistence
3.18.34 Use the following attribute on user/pass and other session specific form fields to disable saving across tabs:
3.19 Scratchpad
3.20 Porting or Merge Down
3.21 Refactoring and Regression
3.22 Test Driven Development (TDD)
3.23 Grunt
3.24 Mock data
3.25 Code Coverage
3.26 Code Review
3.27 Chores
3.28 Automation
3.29 API Design
3.29.1 Usability
3.29.2 Flexibility
3.29.3 Reliability
3.29.4 Maintainability
3.29.5 Security
3.29.6 Integrity
3.29.7 Simplicity
3.29.8 Ubiquity
3.29.8.1 Points of References
3.30 References
[edit]Measurement

[edit]Non-Project Time

Status Meetings
Department Meetings
Company Meetings
Team Meetings
One-on-One Meetings
Compliance Training
Application Training
Framework Training
Goal Setting
Demos
FRD Review
Test Plan Review
Test Case Review
Go/No Go Meeting
ECO Meeting
[edit]Non-Development Project Time

API Diagramming
User Flow Diagramming
Event Diagramming
Responsive Design
Algorithm Design
Test Design
Algorithm Design Review
API Design Review
Responsive Design Review
Developer Collaboration
Business Clarification
Self-Code-Review of Code on Paper
Peer-Code-Review of Code on Screen
Unit Test of Code on Screen
Functional Test of UI
System Test of User Flows
Implementation Design
UAT Promote
Environment Setup
Environment Troubleshooting
Patching
Patch Troubleshooting
Workload Rebalancing
Defect Status Reporting
[edit]Development

Algorithm Implementation time
Algorithm Debugging Time
Layout Prototyping Time
Accessibility Implementation Time
Data Mocking Time
Private API Commenting Time
Public API Documentaton Time
Code Indentation Time
Number of linting defects
Number of styling defects
Number of runtime defects
Number of compilation defects
[edit]Rapid Prototyping

Download comps
Setup download script with the following alias
[edit]jtidy

Get jtidy from maven central:
http://central.maven.org/maven2/net/sf/jtidy/jtidy/r938/jtidy-r938.jar

Alias the file
cp jtidy-r938.jar ~/jtidy.jar
Run the help file
java -jar jtidy.jar -h
Create an alias for it using xargs
vi ~/alias
alias jtidy='xargs | java -jar ~/jtidy.jar'
Run it on a file
cd html
jtidy foo.html
Create a config file

indent: auto
indent-spaces: 2
quiet: yes
tidy-mark: no
doctype: omit
new-blocklevel-tags: main
newline: LF
output-html: yes
show-body-only: yes
trim-empty-elements: no
drop-empty-paras: no
wrap: 148
input-encoding: UTF-8
output-encoding: UTF-8
char-encoding: UTF-8

Save it as config.txt

Run with a config file:

jtidy.jar -config config.txt foo.html


References:
http://api.html-tidy.org/tidy/tidylib_api_5.2.0/tidy_config.html
http://jtidy.sourceforge.net/howto.html
https://stackoverflow.com/q/7151180/1113772
[edit]jsFiddle

Deminify code
Start with working code
Modify with mock data
[edit]Debugging

think: five w's
motivation:jsfiddle
tool:grep
topic:error
progress:logging
answer:hardcoding
solution:parameterization
[edit]Linting

Run JSHint with the following options:
es3: true, // do not allow code which is not valid ECMAScript 3 (for IE8)
jquery: true, // allow access to $ and jQuery
undef: true, // do not allow undefined variables (implicit globals)
Use the following to replace quotes in vim:
1,$ s/=."/=.'/g
[edit]Ten Minute Tasks

[edit]Test Mock Data

Open the JSON file
Copy it to the JS file
Assign it to a global
Add it to the application cache or localStorage
Reference it in the template or bind it to an event
[edit]Sync Copy Deck Text

Open the copy deck
Copy the text
Replace special characters with entities
Paste into the markup or into a script tag with a custom MIME type
Reload the page
[edit]Adding ARIA

Open the template
Add a class to each input
Add a class to each link
Add a class to each button
[edit]Fix Layout

Align left and right bookends
Equalize table columns
Wrap words consistently
Set colors based on style guide
[edit]Test Filters

Create function
Test in console
Wrap in a module
[edit]Start App Server

Checkout webapp instance
Change em.properties
Build instance
Start server
[edit]Setup session

Find an account
Login
update svn
deploy new code
restart server
find a bug
restart putty and rebuild last night's checkins
[edit]Update JIRA

Find stories assigned to you
Related stories assigned to others
Comments on related stories
[edit]Update QC

Check email for reopened defects
Find QC client on desktop
Open QC and search for the defect ID from the email
Add a comment
Set a date for patching
Patch the fix by the date
[edit]30 Minute Tasks

[edit]Parameterize code

Take working code
Replace hardcoded values (var foo = 1) with typed arguments (myfn(foo) {})
[edit]Test Services

Take a URL
Add POST parameters
Get an error
Modify the POST parameters
Lather, rinse, repeat
[edit]Add scripts to index.html

Add code + data in a file
Test in the console
Abstract data from code
Add data in a file
Wrap code into a module namespace
Link code and data in index.html
[edit]Test Controllers

Stub dependencies
Mock state changes
Assert expectations
[edit]Test XSLT

descendent-or-self axis to abstract root dependency
Mock XML for .raw
xsl:message to assert expectations
[edit]60 Minute Tasks

[edit]Trace Errors

Deminify code
Set breakpoint at each variable assignment which maps to an undefined field or empty text node the UI
Set breakpoint at each response from an AJAX request
Find type mismatch(es) and unclosed braces/parentheses
[edit]Create Markup and Styles from Comps

Choose semantic tags based on microformats and WAI-ARIA
Choose styles based on mobile first design
Use imagemagick to crop and optimize images
[edit]Pixel Perfection

Import Bootstrap and page specific CSS into JSFiddle
Use a <style> element for the smallest screen
Use media queries for larger screens
Use generated content for elements that are large screen specific
Use a ruler and a Fibonacci sequence to keep ratios consistent
Do not use inline styles
[edit]120 Minute Tasks

[edit]Generalize Code

Move anonymous functions to named functions
Move private methods to public methods
Move private variables to arguments
Move public methods to separate files
Move private methods to utility files
Move arguments to annotated comments
Move generic markup into separate HTML files
[edit]Unit Test

Add console logs
Add script to generate tests from console logs
Use the DOM to generate mock structures, Math.random to generate mock values, and the Function constructor to generate mock globals
[edit]Integration Testing

Use curl to test exsting JSON APIs
Use node to fake new JSON APIs
Use express to transform XML to JSON or old JSON to new JSON
[edit]Functional Test

Use Bookmarklets to generate globals
Use Selenium to fake events
Use Greasemonkey to fake function calls
[edit]Isolation of Bugs

Open SIT in one browser
Open UAT in another browser
Open Developer Tool in both browsers
Open the same URL in both browsers
Perform the same form submission in both browsers
Compare the request/response for the same form submission
If the issue is in one browser, it is a database difference
If the issue is in both browsers, it is a bug on the client or server
If the issue is 100% reproducible, it is a bug on the server
If the issue is sporadic, it is an issue on the client due to asynchronous network latency
If the issue is hard to reproduce, it is a memory leak on the client or the server
[edit]240 Minute Tasks

[edit]Diagram Flows

Map events to arrows
Map handlers to boxes
Map gaps to question marks
Map data to circles
Map templates to diamonds
[edit]360 Minute Tasks

[edit]Refactor Code

Identify bad code from diffs
Separate functional changes from maintenance changes
Rewrite code to avoid bad code
[edit]480 Minute Tasks

[edit]Error Messaging

Add inline form validation
Add error toggles
Add unit tests
[edit]Rollback and Reapply after Code Freeze

Save current source file to wiki
Revert to trunk revision
Diff trunk vs wiki
Reapply necessary code
Add unit test new code
Add functional test
Split new conditional blocks into services
Add unit tests for each service
[edit]Browser

Disable same origin policy
[edit]IDE

Sync via SFTP
Setup Find/Replace regex to identify missing mock data mappings in AJAX requests
[edit]HTML

Start with prototype markup from creative team
Merge with markup from xeon-shared views directory
Replace ng-controller with a directive when sharing templates
Replace prototype data binding attributes
To clone part of a directive template:
Add an ID attribute to the element in question
Add position:absolute;z-index:-1 to the element
Proxy it via a <label> tag or the :target selector
Identify one-way and two-way bindings for optimization

Use event delegation and services rather than inline events
Add prefetching link metadata to the index.html or index.ftl
[edit]JavaScript

Start with inline events
Add stub function calls
Insert working callbacks without validation
Use the angular.mock.dump() method to dump variables
[edit]CSS

Start with existing markup and class attributes
Extend with inline styles
Decide on new class names
Convert inline styles to new class names
[edit]Boilerplate

index.html with globals
package.json with required libraries
Gruntfile.js with unminified copy tasks
karma.conf.js with _dev-site mapping of code coverage report
[edit]Pseudocode

Start with MVVM (HTML + onclick => module + directive)
Move to flow diagram
Separate UX code (templates) from business logic(events) and performance code (experiments)
[edit]Bootstrap 2

[edit] Fluid Rows (non-floated)

.row-fluid [class*="span"]
[edit] Inline-Block Form Fields

.input-append input[class*="span"]
[edit] Block Form Fields

 input[class*="span"],
 select[class*="span"],
 textarea[class*="span"],
 .uneditable-input
[edit]Bootstrap 3

[edit] No Float

.visible-xs-block.input-group.col-0
[edit] Left aligned Block Row

.row.input-group.col-0
[edit] Indented Row

.input-group.col-0
[edit] Indented Column

.col-xs-offset-1
.col-sm-offset-1
.col-md-offset-1
.col-lg-offset-1
.col-xs-offset-2
.col-sm-offset-2
.col-md-offset-2
.col-lg-offset-2
.col-xs-offset-3
.col-sm-offset-3
.col-md-offset-3
.col-lg-offset-3
[edit] Relative Containers

.carousel
.modal-dialog
[edit] Inline-Block Containers

.visible-xs-inline-block
.visible-sm-inline-block
.visible-md-inline-block
.visible-lg-inline-block
.radio-inline
[edit] Inline-Table

.form-inline .input-group
[edit] Inline-Block Form Fieldset

.form-inline .form-group
[edit] Inline-Block Form Fields

.form-inline .form-control
[edit] 100% Width Grid-Based Blocks

.col-xs-12.input-group.col-0
[edit] 100% Width Grid-Based Inline-Blocks

.col-xs-12.input-group.col-0.visible-xs-inline-block.visible-sm-inline-block.visible-md-inline-block.visible-lg-inline-block
[edit] Justified Inline-Blocks

.text-justify
[edit] Vertical Alignment

.form-inline .control-label
[edit] Centered Blocks:

.center-block
[edit] 25% width:

.col-sm-3
.col-md-3
.col-lg-3
[edit] 50% width:

.col-sm-6
.col-md-6
.col-lg-6
.utility-menu
.page-refresh
[edit] 75% width:

.col-sm-9
.col-md-9
.col-lg-9
[edit] Block containers:

.visible-xs-block
.visible-sm-block
.visible-md-block
.visible-lg-block
[edit] Help content:

.help-block
[edit] Collapsing Margins:

.voffset1
.voffset2
.voffset3
.voffset4
.voffset5
.voffset6
.voffset7
.voffset8
.voffset9
[edit] No outline

.open > a 
[edit] Pseudo href

button .btn-link
[edit] Tooltips

data-toggle="tooltip" data-placement="left" title="Tooltip on left"
[edit]ARIA

[edit] Pressed

aria-pressed="true"
[edit] Hidden

aria-hidden="true"
[edit] Name Label

aria-label="Close"
[edit] Modal Control Indicator

aria-haspopup="true"
[edit] Tab Control Indicator

aria-controls="trade-tab"
[edit]Modal Container

role="dialog"
[edit]Modal Content

role="document"
[edit] Screen Reader

.sr-only (Text)
.sr-only-focusable (Form)
[edit]Persistence

[edit] Use the following attribute on user/pass and other session specific form fields to disable saving across tabs:

autocomplete="off"
[edit]Scratchpad

Deminify library code
Put all script tags inline
Set breakpoints to test assumptions
[edit]Porting or Merge Down

Open trunk and branch files in a diff tool(text-compare.com / kdiff3)
Put the side by side view in one tab, and the remote source view in another
Identify the new code in the side by side view, then copy it from the remote source view
Paste it into the branch, then save the file
Run jshint, find the next diff, then repeat
[edit]Refactoring and Regression

Hardcode new variables
Comment out new blocks of code
Use a hashed array tree + a JSON search utility as a generic function argument for easy extensibility
[{"foo":"hi","bar":"bye","baz":[{"num":123},456]]
Revert to old version, then replace one function at a time
Separate refactoring into three commits:
Add new and modified unit tests, then check in
Add new function statements, then check in
Change existing functions, then check in
[edit]Test Driven Development (TDD)

Map HTML IDs and attributes to events
Map events handlers to expected arguments and global dependencies
Map expectations to Boolean assertions
[edit]Grunt

Setup watch
cd xeon-[retirement|trading] 
nohup grunt watch &
Setup jshint
Setup livereload
[edit]Mock data

Go to app/index.html
Change mock: false to mock: true
[edit]Code Coverage

Go to karma.conf.js
Add a second reporter to output to the root index page of your local nodeJS server
[edit]Code Review

Check crucible
Run svn up
Run jshint
[edit]Chores

File issues for
svn promote issues
spring compilation failure
web server misconfigurations
load balancer policy mismatches
account database corruption
batch job non-existence
[edit]Automation

TortoiseSVN hook for doing svn up before svn commit
End-to-end testing tied to Test Scenarios
Add flowcharts for user stories
Add bulleted list to sub-tasks
Add Interaction story for each sprint
Add Infrastructure story for each sprint
Stop sending email for report blockers
[edit]API Design

[edit]Usability

[edit]Flexibility

[edit]Reliability

[edit]Maintainability

[edit]Security

[edit]Integrity

[edit]Simplicity

[edit]Ubiquity

[edit]Points of References

**References**

https://medium.com/@jordan_mohi/adding-react-to-an-existing-page-fb128fed94ee

https://medium.com/dailyjs/running-mocha-tests-as-native-es6-modules-in-a-browser-882373f2ecb0

https://medium.com/@andy.neale/learning-react-setting-up-a-minimal-react-development-environment-fcd17fc7dee1

https://medium.com/front-end-hacking/how-it-feels-to-learn-javascript-in-2017-a934b801fbe

https://codeburst.io/fastest-way-to-publish-a-vue-js-component-on-npm-d58f59e185f8

https://www.mediawiki.org/wiki/Phabricator/Project_management

http://www.au.af.mil/au/awc/awcgate/army/writing_tips.htm

https://indieweb.org/How_to_publish_and_consume_WebSub