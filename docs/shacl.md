---
hide:
  - navigation
  - toc
---

# SHACL

- Shape 1: [https://s.zazuko.com/dwpSfy](https://s.zazuko.com/dwpSfy){:target="\_blank"}

<div class="grid cards" markdown>

- **Column 1**

  ***

  ```xml
  @prefix sh: <http://www.w3.org/ns/shacl#> .
  @prefix ex: <http://example.com/> .
  @prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
  @prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
  @prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
  @prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
  @prefix owl: <http://www.w3.org/2002/07/owl#> .

  ex:ArtefactShape a sh:NodeShape ;
    sh:targetClass ex:Artefact ;

    sh:property [
      sh:path ex:belongsToHistoricalMovement ;
      sh:datatype xsd:string ;
    ] ;

    sh:property [
      sh:path ex:hasArtist ;
      sh:class ex:Artist ;
    ] ;

    sh:property [
      sh:path ex:hasEndCreationDate ;
      sh:datatype xsd:integer ;
      sh:minCount 1 ;
      sh:maxCount 1 ;
    ] ;

    sh:property [
      sh:path ex:hasStartCreationDate ;
      sh:datatype xsd:integer ;
      sh:minCount 1 ;
      sh:maxCount 1 ;
    ] .
  ```

- **Column 2**

  ***

  ```xml
  @prefix ex: <http://example.com/> .
  @prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
  @prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
  @prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
  @prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
  @prefix owl: <http://www.w3.org/2002/07/owl#> .


  ex:the_last_supper rdf:type ex:Artefact ;
                     ex:belongsToHistoricalMovement "Renaissance" ;
                     ex:hasArtist ex:leonardo_da_vinci ;
                     rdfs:label "The Last Supper" .

  ex:mona_lisa rdf:type ex:Artefact ;
               ex:belongsToHistoricalMovement "Renaissance" ;
               ex:hasArtist ex:leonardo_da_vinci ;
               ex:hasEndCreationDate 1517 ;
               ex:hasStartCreationDate 1503 ;
               rdfs:label "Mona Lisa" .

  ex:leonardo_da_vinci a ex:Artist .
  ```

</div>

- Shape 2: [https://s.zazuko.com/V8CWRc](https://s.zazuko.com/V8CWRc){:target="\_blank"}
