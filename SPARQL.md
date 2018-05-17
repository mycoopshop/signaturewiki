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