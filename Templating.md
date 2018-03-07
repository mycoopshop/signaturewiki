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