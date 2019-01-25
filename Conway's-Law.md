<pre>
Phase         Description
Plan          Plan the work and document the plan
Design        Design the program
Code          Implement the design
Compile       Compile the program and fix and log all defects found
Test          Test the program and fix and log all defects found
Postmortem    Record actual time, defect, and size data on the plan
</pre>

2. Common Mistakes
When working on a specification, there are common mistakes an editor can make when writing conformance requirements that makes them difficult, if not impossible, to test. For technical specifications, the testability of a conformance requirement is imperative: conformance requirements eventually become the test cases that implementations rely on to claim conformance to a specification. If no implementation can claim conformance, or if aspects of the specification are not testable, then the probability of a specification becoming a ratified standard, and, more importantly, achieving interoperability among implementations, is significantly reduced.

The most common mistakes that editors make when writing conformance requirements include, but are not limited to:

Creating conformance requirements for products that don’t have behavior, e.g. “an XML file must be well-formed.” — this cannot be tested since it doesn’t say what the outcome is on that condition.

Using a passive voice for describing the behavior, e.g. “an invalid XML file must be ignored” — this hides what product is supposed to follow the prescribed behavior.

Using under-defined behaviors, e.g. “a user agent must reject malformed XML” without defining the algorithmic process that is to “reject” something — this makes it impossible to define the outcome of the testable assertion.

* https://resources.sei.cmu.edu/asset_files/TechnicalReport/2000_005_001_13751.pdf
* http://wiki.c2.com/?PersonalSoftwareProcess
* https://www.slideshare.net/GurbakashPhonsa/software-quality-isocmmpsp
* https://www.pitt.edu/~ckemerer/PSP_Data.pdf
* https://www.slideshare.net/alanmcsweeney/conways-law-cognitive-diversity-organisation-transformation-and-solution-design-66522207
* https://developer.salesforce.com/blogs/engineering/2015/04/overcommitting-agile-11-practical-solutions-part-2.html
* https://sites.google.com/a/scrumplop.org/published-patterns/product-organization-pattern-language/conway-s-law
* https://skeltonthatcher.com/wp-content/uploads/2017/12/How-to-choose-tools-for-DevOps-and-CD-2017.pdf
* https://www.thoughtworks.com/insights/blog/demystifying-conways-law
* http://dau.dodlive.mil/2015/09/21/requirements-engineering-in-an-agile-software-development-environment/
* https://www.directives.doe.gov/draft/0415.1-EGuide-2-draft/@@images/file
* https://apps.dtic.mil/dtic/tr/fulltext/u2/a512409.pdf
* http://users.csc.calpoly.edu/~jdalbey/301/Forms/PSP0ProcessScript.pdf
* https://www.lanl.gov/projects/CartaBlanca/webdocs/PhippsPaperOnJavaEfficiency.pdf
