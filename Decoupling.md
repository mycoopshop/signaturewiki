>I typically use a MVC design so that I can design the view, link all of the triggers to the controller, and work on the controller/model without ever having to touch the view again. Is there a way to simulate this in web design?

Use event attributes to simulate this:

    <div class="view" onclick="controller('click')" onblur="controller('blur')" onload="controller('load')" onunload="controller('unload')" onerror="controller('error')">
    </div>


> Is there a way just to reduce the coupling feeling? 

Use different languages for each level, such as:

* XML for the Model, XSLT for the View, CSS for the Controller
* JSON for the Model, JSON.parse for the View, AJAX for the Controller
* CSV for the Model, FTP for the View, Socket for the Controller
* Logfile for the Model, SVG for the View, Perl for the Controller 
* SQLite for the Model, CSV for the View, Spreadsheet for the Controller
* hTurtle for the Model, GRDDL for the View, jQuery for the Controller
* Gateway for the Model, PubSub for the View, Proxy for the Controller
* Metadata for the Model, Metaobjects for the View, Metacharacters for the Controller
* Dictionary for the Model, Hashed Array Tree for the View, Dispatch Table for the Controller
* Cache for the Model, Template for the View, Filters for the Controller
* URLs for the Model, URITemplates for the View, URITemplate Parser for the Controller
* Recordset for the Model, Heredoc for the View, Higher Order Functions for the Controller
* indexedDB for the Model, HTML for the View, JSON.stringify for the Controller
* HTML for the Model, CSS for the View, CSSOM for the Controller
* data:URIs for the Model, HTML for the View, CSS for the Controller
* XML for the Model, SVG for the View, SMIL Animation for the Controller
* URLs for the Model, Request Body for the View, Request Headers for the Controller

**References**

* [Reusable XSL Stylesheets and Templates - Tony Marston](http://www.tonymarston.net/xml-xsl/reusable-xsl.html)
* [The hTurtle Microformat](http://inamidst.com/sw/hturtle/)
* [CSS 2.1:Precedence of non-CSS presentational hints](http://www.w3.org/TR/CSS2/cascade.html#preshint)
* [XHTML Flavors comparisons](http://www.w3.org/2007/09/dtd-comparison.html)
* [oneBox](http://www.cssplay.co.uk/menu/oneBox.html)
* [SMIL: Challenges](https://wiki.mozilla.org/SMIL:Challenges)
* [Microsoft Application Architecture Guide, Chapter 8: Data Layer Guidelines](https://msdn.microsoft.com/en-us/library/ee658127.aspx)
* [RIA Services - Enterprise Patterns with WCF RIA Services](https://msdn.microsoft.com/en-us/magazine/ee336308.aspx)
* [Hashed Array Tree Diagram](https://upload.wikimedia.org/wikipedia/commons/0/04/HashedArrayTree16.svg)
* [HTTP: The Request](https://www.w3.org/Protocols/HTTP/Request.html)
* [URL Session Programming Guide: About the URL Loading System](https://developer.apple.com/library/tvos/documentation/Cocoa/Conceptual/URLLoadingSystem/URLLoadingSystem.html)
* [C#, Web API: HTTP GET with a Request Body](http://www.codeproject.com/Articles/849034/Csharp-Web-API-HTTP-GET-with-a-Request-Body)
* [JMESPath: A query language for JSON](http://jmespath.org/)
* [Encoding Dublin Core Metadata in HTML](https://www.ietf.org/rfc/rfc2731.txt)
* [DBI recipes](http://www.perlmonks.org/?node_id=284436)
* [Ots Labs: Ots Media Query Language (OMQL) Documentation](http://www.otslabs.com/omql-docs/)
* [js.html - Haxe API](http://api.haxe.org/js/html/)
* https://stackoverflow.com/questions/804751/1113772
* https://stackoverflow.com/questions/16435711/1113772
* https://stackoverflow.com/questions/19618767/1113772
* https://stackoverflow.com/questions/18273772/1113772
* https://stackoverflow.com/questions/7326405/1113772
* https://stackoverflow.com/questions/14902466/1113772
* https://stackoverflow.com/questions/14995037/1113772
* https://stackoverflow.com/questions/15108544/1113772
* https://stackoverflow.com/questions/6209157/1113772
* https://stackoverflow.com/questions/12288820/1113772
* https://stackoverflow.com/questions/12710122/1113772