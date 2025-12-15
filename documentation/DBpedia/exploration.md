## Tests requêtes

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


  PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX dbo: <http://dbpedia.org/ontology/>
SELECT DISTINCT ?p ?o1 
WHERE { 
  dbr:List_of_fantasy_authors ?p ?o1.
  ?o1 a dbo:Person.
  }
LIMIT 10

résultat: 	http://dbpedia.org/resource/Karl_Edward_Wagner
	http://dbpedia.org/resource/Mark_Lawrence_(author)
http://dbpedia.org/resource/John_Bellairs
http://dbpedia.org/resource/Kenneth_Bulmer
http://dbpedia.org/resource/Lloyd_Arthur_Eshbach
	http://dbpedia.org/resource/William_Nicholson_(writer)
	http://dbpedia.org/resource/David_Drake
	http://dbpedia.org/resource/John_Crowley_(author)
	http://dbpedia.org/resource/Christopher_Moore_(author)
	http://dbpedia.org/resource/Jean-Louis_Fetjaine



Situer dans le web sémantique:
PREFIX dbr: <http://dbpedia.org/resource/>
PREFIX dbo: <http://dbpedia.org/ontology/>
SELECT ?person ?object
WHERE { 
dbr:List_of_fantasy_authors ?p ?person.
?person a dbo:Person;
        dbo:birthDate ?birthDate ;
    <http://www.w3.org/2002/07/owl#sameAs> ?object.
    BIND(xsd:integer(SUBSTR(STR(?birthDate), 1, 4)) AS ?birthYear)
    FILTER ( ?birthYear > 1770)
}
LIMIT 100