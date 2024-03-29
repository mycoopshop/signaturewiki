# Living Without Sessions

When we talk about sessions in Web app development, we're usually talking about server stored data about a particular client. Some Web frameworks use session state to track and hold information about the user throughout their journey through the site, however they go against the RESTful principles and should really be treated as a bug.

Developers became used to having sessions available to them, so when systems grew, became more complex, and started spreading over multiple servers, more and more hacks had to be introduced to keep the session support working, when in reality, sessions should never have been introduced in the first place.

This article isn't to argue the pros and cons of server sessions, you can research that for yourself on the Web, we're going to look at an example system that is commonly built using sessions and how we can avoid sessions and come up with a better system.

Building a shopping cart with sessions

We're going to look at a standard shopping cart application, it will do the usual, display a bunch of products to the client and allow them to place them into their cart.

With sessions, we'd create a session, tie it to the client, and use it to store the IDs of each product the user places in their basket. Great, until we get a gazillion users and our server burns up in a firey memory related hell or we try to load balance across multiple servers so we need to buy expensive load balancers with layer 7 sticky session support. Yuk! There must be a better way, well infact there isn't a better way, there are two.

Cart on the client

When you think about someone in real life going into a shop and placing items into their shopping basket, where is the basket? It's with the user. So why don't we model our online shop to mirror the real life scenario.

Web browsers used to be a document reader for displaying hypertext documents transfered over the HTTP protocol, but nowerdays they are an application platform thanks to the development and deployment of Javascript within the HTML document and the browser. So we can use Javascript to extend our clients browser to be able to store their shopping cart until they reach the checkout.

We have to do a little work to make the browser hold it's state between page requests. We have a few choices:

Place the catelogue part of the site in a frameset with a "basket" frame that stores and displays the users basket to them. Pretty easy to do but not great since frames are a usability nightmare and we have to do extra work to provide bookmarkable URLs to individual products.
Expect the client to also support cookies and stuff the cart data in there. Very easy to do and they can persist for as long as we need, but cookies weren't designed for client state storage and they'll be sent to the server with every request when we only need them to be available to our client.
Wait until the WHATWG Web Application 1.0 spec is finished and implemented in browsers and use the new sessionStorage object.
Cart on the server

On the server, isn't that the same as storing a session on the server?

Yes and no. We can store the users cart on the server as long as we do it in a RESTful way we won't hit any of the problems associated with user sessions. The problem with sessions is that we're storing client state on the server, however if we don't treat the clients cart as being part of their state and rather treat it as being part of the shop itself, then we can get around the problems with sessions.

Imagine a shop where rather than being self-service, there is a shopkeeper who upon being asked, goes and fetches the items you want and rings them up on the till. Now if we were to model that as our online shop we'd see that the client no longer has a basket as part of their state, the basket is part of the shop.

So how would this work? Looking at the interactions between the client and the server, it might look something like this:

Client

Show me your products.

Server

Here's a list of all the products you can buy at this shop.

Client

Good, okay, I'd like to buy 1 of http://example.org/shop/product/X, please place it in my basket, my username is "JohnDoe" and my password is "secretPassword".

Server

Okay, I've added 1 of http://example.org/shop/product/X into your basket, you can review your basket at http://example.org/shop/users/johndoe/basket

Client

I'd like to buy 1 of http://example.org/shop/product/Y as well, please place one in my basket, my username is "JohnDoe" and my password is "secretPassword".

Server

Okay, I've added 1 of http://example.org/shop/product/Y into your basket as well, you can still review your basket at http://example.org/shop/users/johndoe/basket

Client

Actually I don't want http://example.org/shop/product/X after all, please remove it from my cart, my username is "JohnDoe" and my password is "secretPassword".

Server

Okay, I've removed http://example.org/shop/product/X from your basket, you can review your updated basket at http://example.org/shop/users/johndoe/basket

Client

Okay I'm done, ring 'em up, my username is "JohnDoe" and my password is "secretPassword".

Server

Should I charge that to your expense account?

The thing to notice about this conversation is that it is stateless, every action from the client is independent of any other. This means that at any time, the user can run off and do something else, come back a few days later and carry on. It also means they could get some other service to add things to their shopping basket easily.

Ain't that just a session?
So how does this differ from storing the cart in a user session on the server? After all doesn't the conversation above also apply no matter whether we're storing the cart in a session or in a resource?

Firstly a users session is transitory, it's there when the user is there, but will be cleaned up and lost once they leave, in our RESTful design the cart is as integral as a user account, so whatever means we use to store and process user accounts we use to store and process the users cart (so it might be a MySQL database cluster with Memcached in front of it).

Secondly we can grab hold of the users cart since it's a resource that has a URL, so we can query and manipulate it at will, pass the URL to other services, etc.

The differences can seem very subtle, but it's the subtleties that make the difference, since we're explicitly creating and adjusting resources on the server all the problems of session handling disappear and are covered by our resource handling solution (our DB cluster for example).

Conclusion

Avoiding sessions is a bit of a purest stance, but it does lead to a more scalable and usable Web app. Keeping the clients state on the client is always a good idea, you can't scale better than by utilising someone elses computer, of course depending on your application and the technologies you are using your mileage may vary.

If you do find you need to store transitory client data on the server, think about re-working that data or the way your app. works so that the data has meaning, give it a URL and turn it into a resource the user can manipulate.


<li> - array <a> - linked list <html> - tree <table> - graph <object> - stack


## References
1. https://blog.bengalbraith.com/2013/06/19/dont-make-second-class-apis/
1. http://help.micro.blog/2017/api-posting/
1. https://usermanual.wiki/Pdf/API20Management20An20Architects20Guide20to20Developing20and20Managing20APIs20for20Your20Organization.46543576/html
1. https://www.xml.com/articles/2017/06/03/simplifying-xml-microxml/
1. http://ajaxian.com/archives/canvas-color-cycling
1. http://imrannazar.com/GameBoy-Emulation-in-JavaScript:-The-CPU
1. https://code.google.com/archive/p/canto-js/
1. http://vertx.io/docs/
1. http://ajaxian.com/archives/shim-uses-node-js-to-test-sites-on-multiple-browsers
1. http://ajaxian.com/archives/a-simple-random-bit-on-var-selector
1. http://ajaxian.com/archives/best-practices-for-test-revisited
1. http://ajaxian.com/archives/jdrop-json-in-the-cloud
1. http://ajaxian.com/archives/normal-mapped-lighting-for-photos-using-canvas
1. https://www.iab.com/wp-content/uploads/2016/04/VAST4.0_Updated_April_2016.pdf
1. https://www.codeproject.com/Articles/474905/Using-BizTalk
1. http://www-01.ibm.com/support/docview.wss?uid=swg21633648
1. https://www.ibm.com/support/knowledgecenter/en/SS9H2Y_7.5.0/com.ibm.dp.doc/json_jsontransformationexample3.html
1. https://www.ibm.com/support/knowledgecenter/en/SS9H2Y_7.5.0/com.ibm.dp.doc/xquery_functions.html
1. https://developer.ibm.com/answers/questions/379755/how-to-convert-json-to-soap-in-datapower.html
1. https://toddysm.com/2017/02/02/are-enterprises-building-incomplete-cicd-pipelines/
1. https://creately.com/diagram/example/i7c02ojz1/DevOps%20-%20Infrastructure%20Architecture
1. http://rundeck.org/stories/john_desposito.html
1. http://www-03.ibm.com/certify/assets/content/studyguides/stuc1000_005.pdf
1. https://www.w3.org/wiki/Activity_Streams/Examples
1. https://www.w3.org/TR/activitystreams-vocabulary/
1. https://www.w3.org/TR/social-web-protocols/#bib-Micropub
1. https://www.w3.org/TR/pwp-ucr/
1. https://www.w3.org/TR/SVG2/Overview.html
1. https://playbook.cio.gov/
1. http://www.brising.com/slamdunk2.html
1. https://www.microsoft.com/en-us/research/wp-content/uploads/2013/01/posix-emulation-submitted.pdf
1. https://devcenter.heroku.com/articles/architecting-apps
1. http://www.dtic.mil/docs/citations/ADA572590
1. https://hackernoon.com/o-api-an-alternative-to-rest-apis-e9a2ed53b93c
1. https://blog.shaunfinglas.co.uk/2015/10/header-interfaces-vs-role-interfaces.html
1. https://blog.heroku.com/react-refetch
1. https://blog.heroku.com/deploying-react-with-zero-configuration
1. http://willschenk.com/bot-design-patterns/
1. https://www.storyblok.com
1. https://www.ibm.com/developerworks/cloud/library/cl-lightweight-integration-1/index.html
1. https://www.ibm.com/developerworks/cloud/library/cl-lightweight-integration-2/index.html
1. https://www.ibm.com/developerworks/cloud/library/cl-lambda-functions-rapid-prototyping/index.html
1. https://www.ibm.com/developerworks/java/library/j-javaee8-json-binding-4/index.html
1. https://www.ibm.com/developerworks/web/library/wa-schemaorg1/index.html
1. https://www.ibm.com/developerworks/opensource/library/wa-schemaorg2/index.html
1. https://www.ibm.com/developerworks/opensource/library/wa-schemaorg3/index.html
1. https://www.ibm.com/developerworks/opensource/library/wa-schemaorg4/index.html
1. http://ediacademy.com/blog/walmart-edi-testing-2/
1. https://cdn.corporate.walmart.com/5d/8d/897b4bb84a95bb05214bf897cee3/edi-getting-started-guide.pdf
1. https://www.mediawiki.org/wiki/Manual:MediaWiki_architecture
1. https://www.mediawiki.org/wiki/Wikibase/DataModel/JSON
1. https://www.slideshare.net/balancedteam/lean-engineering-for-leanbalanced-teams-lessons-learned-and-still-learning-bringing-lean-to-paypal
1. https://engineering.linkedin.com/frontend/new-technologies-new-linkedin-home-page
1. https://engineering.linkedin.com/blog/2016/01/smashing-the-monolith
1. https://hackernoon.com/webhook-vs-api-whats-the-difference-8d41e6661652
1. https://developer.mozilla.org/en-US/docs/Mozilla/IPDL/Tutorial
1. https://www.mobilize.net/blog/vb6-to-microservices-is-it-even-a-thing
1. https://www.marklogic.com/blog/data-integration-wizard-talks-microservices-containers-data-governance/
1. https://www.marklogic.com/blog/microservices-persistence-benefits-risks/
1. https://hal.archives-ouvertes.fr/hal-01783936/file/sparql-micro-services-poster.pdf
1. https://www.slideshare.net/barthanssens/publishing-rdf-skos-with-microservices
1. http://events.linkeddata.org/ldow2018/papers/LDOW2018_paper_1.pdf
1. http://ceur-ws.org/Vol-1629/paper4.pdf
1. https://www.gnu.org/software/emacs/emacs-paper.html