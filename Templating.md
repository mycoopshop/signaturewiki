The [W3 Word Processor Filters page](http://www.w3.org/Tools/Word_proc_filters.html) should answer most of these questions. For more details, here some resources on the evolution of separating content from presentation:

 * [Groff Mission Statement (pdf)](http://www.gnu.org/software/groff/groff-mission-statement.pdf)
 * [The Roots of SGML -- A Personal Recollection](http://www.sgmlsource.com/history/roots.htm)
 * [Java FAQ](http://www.cafeaulait.org/javafaq.html)
 * [Charles Goldfarb—the Godfather of Markup Languages](http://history-computer.com/Internet/Birth/Goldfarb.html)
 * [Markup Language Family Tree](http://www.jkemp.net/blog/2011/04/)
 * [Typesetting with Linux](http://www.antipope.org/charlie/old/linux/shopper/159.typesetting.html)
 * [A Triumph of Simplicity: James Clark on Markup Languages and XML](http://www.drdobbs.com/a-triumph-of-simplicity-james-clark-on-m/184404686)
 * [Markup and Style: History and Philosophy](http://www.cs.sfu.ca/~cameron/Teaching/470/markup1.html)
 * [Catalog of compilers, interpreters, and other language tools](http://www.faqs.org/faqs/compilers/free/part5/)
 * [Understanding the Taxonomy of Languages: Chapter 8 - Minilanguages](http://www.catb.org/esr/writings/taoup/html/ch08s01.html)
 * [SGML: In Memory of William W. Tunnicliffe](http://xml.coverpages.org/tunnicliffe.html)
 * [A Companion to Digital Humanities: Allen H. Renear - Text Encoding](http://www.digitalhumanities.org/companion/view?docId=blackwell/9781405103213/9781405103213.xml&chunk.id=ss1-3-5)
 * [Drawing inferences on the basis of markup](http://conferences.idealliance.org/extreme/html/2002/CMSMcQ01/EML2002CMSMcQ01.html)
 * [Rabbit/duck grammars: a validation method for overlapping structures](http://conferences.idealliance.org/extreme/html/2006/SperbergMcQueen01/EML2006SperbergMcQueen01.html)
 * [Markup Languages and (Non-) Hierarchies](http://xml.coverpages.org/hierarchies.html)
* https://varnish-cache.org/docs/3.0/tutorial/esi.html
* https://symfony.com/doc/current/http_cache/esi.html
* https://www.fastly.com/blog/using-esi-part-1-simple-edge-side-include/
* https://www.w3.org/TR/esi-invp
* https://www.w3.org/TR/edge-arch/
* https://www.npmjs.com/package/xmlpug
* https://www.npmjs.com/package/json-transforms
* https://www.balisage.net/Proceedings/vol19/html/Lumley01/BalisageVol19-Lumley01.html
* http://www.saxonica.com/papers/xmlprague-2018mhk.pdf
* https://doc-snapshots.qt.io/qtivi/template-syntax.html
* https://shripadk.github.io/react/docs/jsx-gotchas.html
* http://blog.vjeux.com/2013/javascript/jsx-e4x-the-good-parts.html
* https://github.com/facebook/react/issues/11845
* https://stackoverflow.com/questions/30852751/expected-corresponding-jsx-closing-tag-for-input-reactjs
* https://stackoverflow.com/questions/26354600/how-do-you-make-react-js-output-valid-xml-instead-of-html
* [AtomPub vs CMIS](https://www.oasis-open.org/committees/download.php/30907/CMIS%20--%20REST%20and%20HTTP%20--%20Dave%20N%20--%201-27-2009.pdf)
* [Freemarker vs Velocity](http://deepak-keswani.blogspot.com/2011/09/freemarker-vs-velocity-ftl-vs-vm.html)
* [OpenCms Documentation | Multilingual websites](https://documentation.opencms.org/opencms-documentation/localization/multilingual-websites/)

Markup and typesetting languages are the earliest examples of templating. Here is the Wikipedia definition:
>A markup language is a modern system for annotating a document in a way that is syntactically distinguishable from the text. The idea and terminology evolved from the "marking up" of manuscripts, i.e., the revision instructions by editors, traditionally written with a blue pencil on authors' manuscripts. Examples are typesetting instructions such as those found in troff and LaTeX, or structural markers such as XML tags.

Here is a diagram:
<pre>
                        RUNOFF                      "Generic Coding"                 "Editorial Structure Tags"
                   (Jerome Saltzer, 1964)         (William Tunnicliffe, 1967)          (Stanley Rice, pre-1970)
                            |                               |                                     |
                            |                               |                                     |
        TeX          roff - nroff - troff                   |-------------------------------------|
 (Don Knuth, 1977)   (Josef Osanna, 1973)                   |
                                                           GML
                                                    (Charles Goldfarb, 1969)
                                                            |                       SCRIBE
                                                            |                   (Brian Reid, 1980)
                                                            |                          |
                                                            |--------------------------|
                                                          SGML
                                                      (Standard, 1980)
                                                     |                |
                                                     |                |
                                                   HTML              XML
                                            (Berners-Lee, 1990)    (Standard, 1998)
</pre>
As far as web site templating, [SSI](http://www.webreference.com/programming/ssi/index.html) is the mother of them all.


From a security standpoint, JSP scriptlets have vulnerabilities:

>There are a handful of objects made available in JSPs which are susceptible to security flaws. Their corresponding Java class functions are used as is in scriptlets. All the same security rules should apply.
 
For example, one session variable:

     <%=session.getAttribute(name)%>

can taint another:

    <% 
    String name = request.getParameter("username");
    session.setAttribute("taintedAttribute", name);
    %>

and unescaped strings can be dangerous as well:

    <style>
    <%
      String parm = request.getParameter("foobar");
      String cssEscaped = Escape.cssString(parm);
    %>

    a[href *= "<%= cssEscaped %>"] {
       background-color: pink!important;
    }
    </style>
  
**References**

* [JSP JSTL - OWASP](https://www.owasp.org/index.php/JSP_JSTL)

* [Why Haven’t We Stamped Out SQL Injection and XSS Yet? (pdf)](https://www.rsaconference.com/writable/presentations/file_upload/asec-f42.pdf)

* [Common Attacks on JSP Pages | Securing Servlets and JSPs in Sun Java System Application Server, Part 2 | InformIT](http://www.informit.com/articles/article.aspx?p=1334089&seqNum=4)

* [Refactoring JSP Scriptlets using JSTL and MVC Architecture | LinkedIn](https://www.linkedin.com/pulse/refactoring-jsp-scriptlets-using-jstl-mvc-amir-boroumand/)

* [10 Reasons to replace your JSPs with Freemarker Templates](https://blog.stackhunter.com/2014/01/17/10-reasons-to-replace-your-jsps-with-freemarker-templates/)

* [The Good and Bad parts of JSX – Roman Liutikov – Medium](https://medium.com/@roman01la/the-good-and-bad-parts-of-jsx-33d01ea5c21f)

* [How can I securely use CSS-in-JS with React?](https://reactarmory.com/answers/how-can-i-use-css-in-js-securely)

* [React Issue #1545: Escaping curly brackets](https://github.com/facebook/react/issues/1545)

* [A closer look at Underscore templates](http://2ality.com/2012/06/underscore-templates.html)

* [underscore.js | vAnnotate annotations](http://www.vannotate.com/examples/underscore.html)

* [How to use EJS Templating in a Node.js Application – freeCodeCamp](https://medium.freecodecamp.org/how-to-use-ejs-templating-in-a-node-js-application-ea9347a96c65)

* [Markdown – Harp, the static web server with built-in preprocessing](http://harpjs.com/docs/development/markdown)

* [Can I use a FreeMarker template with AngularJS? - Quora](https://www.quora.com/Can-I-use-a-FreeMarker-template-with-AngularJS)

* [reactjs - How to use sideNav of materialize css with react? - Stack Overflow](https://stackoverflow.com/questions/48911593/how-to-use-sidenav-of-materialize-css-with-react?rq=1)

* [Toby's Brain Dump ...: Sitemesh, my favourite web development companion](http://tmjee.blogspot.com/2012/11/sitemesh-my-favourite-web-development.html)

* [Introduction to SiteMesh Blog | Oracle Community](https://community.oracle.com/docs/DOC-983328)

* [Captain Debug's Blog: Adding Sitemesh to your Spring webapp](http://www.captaindebug.com/2011/09/adding-sitemesh-to-your-spring-webapp.html)

* [9.14. Using FreeMarker in a Web Application - Jakarta Commons Cookbook [Book]](https://www.safaribooksonline.com/library/view/jakarta-commons-cookbook/059600706X/ch09s15.html)

* [The htp and htf Packages](https://docs.oracle.com/cd/B14099_19/web.1012/b15896/pshtp.htm)

* [HTP](https://docs.oracle.com/cd/B28359_01/appdev.111/b28419/w_htp.htm#BABGJJIH)