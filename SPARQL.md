# WikiData Query Autocomplete Documentation
1. Prefix words with "?" to autocomplete subjects
2. Prefix words with "wdt:" or "wd:" to autocomplete objects

**References**
* https://www.youtube.com/watch?v=6qc8ytfgAOw
* https://www.youtube.com/watch?v=bifqad-SG4k
* https://www.youtube.com/watch?v=645bk8HQ4aw
* https://www.wikidata.org/wiki/Wikidata:SPARQL_tutorial
* https://www.w3.org/2007/03/RdfRDB/papers/seaborne.html
* https://www.cambridgesemantics.com/blog/semantic-university/learn-sparql/sparql-vs-sql/
* https://query.wikidata.org/
* https://www.wikidata.org/wiki/Property:P1661
* https://www.wikidata.org/wiki/Property:P856
* https://www.wikidata.org/wiki/Property:P585
* https://www.w3.org/TR/sparql11-results-json/
* https://docs.marklogic.com/guide/semantics/semantic-searches
* https://ontotext.com/power-visualization-graphdb/
* https://docs.oracle.com/cd/E11882_01/appdev.112/e25609/sdo_rdf_concepts.htm#RDFRM595
* https://www.wikidata.org/wiki/Wikidata:WikiProject_Books
* https://franz.com/agraph/support/documentation/current/sparql-tutorial.html
* https://www.xml.com/pub/a/2007/03/14/a-relational-view-of-the-semantic-web.html
* http://www.oraclealchemist.com/news/linked-data-rdf-and-sparql-part-1/
* https://docs.oracle.com/en/database/oracle/oracle-database/18/rdfrm/spatial-and-graph-rdf-semantic-graph-developers-guide.pdf
* https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3073186/
* https://www.cambridgesemantics.com/blog/semantic-university/learn-sparql/sparql-nuts-bolts/
* https://www.cambridgesemantics.com/blog/semantic-university/learn-sparql/sparql-vs-sql/
* https://hal.archives-ouvertes.fr/hal-01245883/document
* https://www.topquadrant.com/2014/05/05/comparing-sparql-with-sql/
* http://explore.dublincore.net/about/
* https://eprints.soton.ac.uk/397863/1/sparql2sql.pdf
* http://people.csail.mit.edu/rivest/Sexp.txt

    SELECT Person.fname, Address.city
    FROM Person, Address
    WHERE Person.addr=Address.ID
    AND Address.state=”MA”

Conceptually, we are SELECTing a list of attributes FROM a set of tables WHERE certain constraints are met. These constraints capture the relationships implicit in the scheme, Person.addr=Addresses.ID, and the selection criteria, e.g. Address.state=”MA”.

A SPARQL query of the same data could look like

    SELECT ?name ?city
    WHERE {
    ?who <Person#fname> ?name ;
    <Person#addr> ?adr .
    ?adr <Address#city> ?city ;
    <Address#state> “MA”
    }


    SELECT ?reaction ?p ?o
    WHERE {
    ?compound ex:name “illudium phosdex” ;
    ?reaction ex:involves ?compound ;
    ?reaction ?p ?o
    }

In SQL, this would be like:

    SELECT reactions.*
    FROM reactions, compounds
    WHERE reactions.compoundID=compounds.ID
    AND compounds.name=”illudium phosdex”