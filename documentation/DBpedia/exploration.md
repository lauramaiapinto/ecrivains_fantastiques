

https://en.wikipedia.org/wiki/Patrick_Rothfuss URL

http://dbpedia.org/resource/Patrick_Rothfuss URI

première requête:

PREFIX dbr: <http://dbpedia.org/resource/>
SELECT *
WHERE 
{
  <http://dbpedia.org/resource/Patrick_Rothfuss> ?p?o
}

Effectif population: 569

PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX dbo: <http://dbpedia.org/ontology/>
SELECT (COUNT(*) as ?eff)
WHERE { 
dbr:List_of_fantasy_authors ?p ?o1.
?o1 a dbo:Person.
  }