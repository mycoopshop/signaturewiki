# WikiData Query Autocomplete Documentation
1. Prefix words with "?" to autocomplete subjects
2. Prefix words with "wdt:" or "wd:" to autocomplete objects

# Flow

    select alexa rank > 500; get website where alexa > 500

# Syntax

    # Demonstrates filtering for value greater than a real number
    SELECT DISTINCT ?alexarank ?website ?websiteLabel ?sitelink 
    WHERE
    {
	?website wdt:P1661 ?alexarank.
        OPTIONAL{ ?website wdt:P856 ?sitelink }
	FILTER (?alexarank < 200) .
	SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en" }
    }
    ORDER BY ?alexarank
# URL
    https://query.wikidata.org/#%23%20Demonstrates%20filtering%20for%20value%20greater%20than%20a%20real%20number%0ASELECT%20DISTINCT%20%3Falexarank%20%3Fwebsite%20%3FwebsiteLabel%20%3Fsitelink%20%0AWHERE%0A%7B%0A%09%3Fwebsite%20wdt%3AP1661%20%3Falexarank.%0A%20%20%20%20OPTIONAL%7B%20%3Fwebsite%20wdt%3AP856%20%3Fsitelink%20%7D%0A%09FILTER%20%28%3Falexarank%20<%20200%29%20.%0A%09SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20"%5BAUTO_LANGUAGE%5D%2Cen"%20%7D%0A%7D%0AORDER%20BY%20%3Falexarank

**References**
* https://www.youtube.com/watch?v=6qc8ytfgAOw
* https://www.youtube.com/watch?v=bifqad-SG4k
* https://www.youtube.com/watch?v=645bk8HQ4aw
* https://www.w3.org/2009/Talks/0615-qbe/
* https://www.w3.org/TR/ld-glossary/
* https://www.w3.org/2003/glossary/subglossary/rdf-mt.rdf/
* https://en.wikibooks.org/wiki/SPARQL/FILTER
* https://www.wikidata.org/wiki/Wikidata:SPARQL_tutorial
* https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/suggestions
* https://www.wikidata.org/wiki/Wikidata:SPARQL_query_service/queries
* https://www.wikidata.org/wiki/Wikidata_talk:SPARQL_query_service/queries
* https://upload.wikimedia.org/wikipedia/commons/d/d6/Wikidata%27s_SPARQL_introduction_presentation.pdf
* https://en.wikibooks.org/wiki/SPARQL/Expressions_and_Functions
* https://en.wikibooks.org/wiki/SPARQL/WIKIDATA_Qualifiers,_References_and_Ranks
* http://index-of.co.uk/Artificial-Intelligence/Morgan.Kaufmann.Semantic.Web.for.the.Working.Ontologist.May.2008.pdf
* http://download.oracle.com/otndocs/tech/semantic_web/pdf/semtech_datamining_v8.pdf
* https://franz.com/agraph/support/documentation/current/sparql-reference.html
* https://www.cambridgesemantics.com/blog/semantic-university/learn-sparql/sparql-nuts-bolts/
* https://www.cambridgesemantics.com/blog/semantic-university/learn-sparql/sparql-vs-sql/
* https://www.cambridgesemantics.com/blog/semantic-university/learn-sparql/sparql-vs-sql/
* https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5856163/
* https://www.w3.org/2007/03/RdfRDB/papers/seaborne.html
* https://www.slideshare.net/jelabra/introduction-to-sparql-83806610
* https://www.slideshare.net/OpenDataSupport/introduction-to-rdf-sparql
* https://www.slideshare.net/_Emw/an-ambitious-wikidata-tutorial
* https://sites.tufts.edu/liam/2014/02/27/sparql/
* http://dig.csail.mit.edu/2010/Courses/6.898/resources/sparql-tutorial.pdf
* https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4893829/
* https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2656016/
* https://www.oit.va.gov/library/programs/ts/edp/dataSharing/DataIntegrationwithSWT_v1.pdf
* https://franz.com/agraph/cresources/white_papers/SemWeb-Language-Primer.pdf
* http://www.biomedbridges.eu/sites/biomedbridges.eu/files/training/1_-_introduction_to_rdf.pdf
* http://www.semantic-web-book.org/w/images/9/94/W2011-03-rdf.pdf
* http://marenas.sitios.ing.uc.cl/talks/pods11.pdf
* https://www.cs.purdue.edu/homes/aref/Spring2018CS348/slides/w9.1-Introduction-to-the-Semantic-Web-Databases-v1.pdf
* http://www.cs.rpi.edu/academics/courses/fall07/semantic/CH4.pdf
* http://ceur-ws.org/Vol-1963/paper576.pdf
* https://query.wikidata.org/
* https://www.wikidata.org/wiki/Wikidata:List_of_properties/all_in_one_table
* https://www.wikidata.org/wiki/Help:Dates
* https://www.wikidata.org/wiki/Property_talk:P585
* https://docs.data.world/tutorials/sparql/list-of-sparql-filter-functions.html
* https://www.w3.org/TR/sparql11-results-json/
* https://github.com/neveldo/TextGenerator
* https://docs.marklogic.com/guide/semantics/semantic-searches
* https://ontotext.com/power-visualization-graphdb/
* https://docs.oracle.com/cd/E11882_01/appdev.112/e25609/sdo_rdf_concepts.htm#RDFRM595
* https://www.wikidata.org/wiki/Wikidata:WikiProject_Books
* https://franz.com/agraph/support/documentation/current/sparql-tutorial.html
* https://www.xml.com/pub/a/2007/03/14/a-relational-view-of-the-semantic-web.html
* http://www.oraclealchemist.com/news/linked-data-rdf-and-sparql-part-1/
* https://docs.oracle.com/en/database/oracle/oracle-database/18/rdfrm/spatial-and-graph-rdf-semantic-graph-developers-guide.pdf
* https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3073186/
* https://hal.archives-ouvertes.fr/hal-01245883/document
* https://www.topquadrant.com/2014/05/05/comparing-sparql-with-sql/
* http://explore.dublincore.net/about/
* http://www.site.uottawa.ca/~diana/csi5180/AIMagzine-DeepQA.pdf
* https://eprints.soton.ac.uk/397863/1/sparql2sql.pdf
* http://people.csail.mit.edu/rivest/Sexp.txt
* https://docs.aws.amazon.com/neptune/latest/userguide/bulk-load-tutorial-format-rdf.html

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