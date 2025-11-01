---
hide:
  - navigation
  - toc
---

# SHACL

## Shape 1: [https://s.zazuko.com/zz9hwp](https://s.zazuko.com/zz9hwp){:target="\_blank"}

<div class="grid cards" markdown>

```
### SHACL shape ###
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
  ] .
```

```
### Data graph ###
@prefix ex: <http://example.com/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .


###  http://example.com/leonardodavinci
ex:leonardo_da_vinci rdf:type owl:NamedIndividual ,
                            ex:Artist ;
                   rdfs:label "Leonardo Da Vinci" .


###  http://example.com/thelastsupper
ex:thelast_supper rdf:type owl:NamedIndividual ,
                          ex:Artefact ;
                 ex:hasArtist ex:leonardo_da_vinci ;
                 ex:belongsToHistoricalMovement "Renaissance" ;
                 rdfs:label "The Last Supper" .
```

</div>

## Shape 2: [https://s.zazuko.com/V8CWRc](https://s.zazuko.com/V8CWRc){:target="\_blank"}

<div class="grid cards" markdown>

```
### SHACL shape ###
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

```
### Data graph ###
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

## Shape 3: [https://s.zazuko.com/7AUrp7](https://s.zazuko.com/7AUrp7){:target="\_blank"}

<div class="grid cards" markdown>

```
### SHACL shape ###
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

ex:PaintingShape a sh:NodeShape ;
  sh:targetClass ex:Painting ;

  sh:property [
    sh:path ex:hasPaintType ;
    sh:datatype xsd:string ;
  ] .

ex:SculptureShape a sh:NodeShape ;
  sh:targetClass ex:Sculpture ;

  sh:property [
    sh:path ex:hasSculptureMaterial ;
    sh:datatype xsd:string ;
  ] .
```

```
### Data graph ###
@prefix ex: <http://example.com/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .

ex:the_last_supper rdf:type ex:Painting ;
                   ex:hasArtist ex:leonardo_da_vinci ;
                   ex:belongsToHistoricalMovement "Renaissance" ;
                   ex:hasEndCreationDate 1498 ;
                   ex:hasPaintType "Mural Paint" ;
                   ex:hasStartCreationDate 1494 ;
                   rdfs:label "The Last Supper" .

ex:mona_lisa rdf:type ex:Painting ;
             ex:hasArtist ex:leonardo_da_vinci ;
             ex:belongsToHistoricalMovement "Renaissance" ;
             ex:hasEndCreationDate 1517 ;
             ex:hasPaintType "Oil paint" ;
             ex:hasStartCreationDate 1503 ;
             rdfs:label "Mona Lisa" .

ex:david rdf:type ex:Sculpture ;
         ex:hasArtist ex:michelangelo ;
         ex:belongsToHistoricalMovement "Renaissance" ;
         ex:hasEndCreationDate 1504 ;
         ex:hasSculptureMaterial "Marble" ;
         ex:hasStartCreationDate 1501 ;
         rdfs:label "David" .

ex:leonardo_da_vinci rdf:type ex:Artist ;
                     rdfs:label "Leonardo Da Vinci" .

ex:michelangelo rdf:type ex:Artist ;
                rdfs:label "Michelangelo" .
```

</div>

## Shape 4: [https://s.zazuko.com/BsgYZW](https://s.zazuko.com/BsgYZW){:target="\_blank"}

<div class="grid cards" markdown>

```
### SHACL shape ###
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

ex:PaintingShape a sh:NodeShape ;
  sh:targetClass ex:Painting ;

  sh:property [
    sh:path ex:hasPaintType ;
    sh:datatype xsd:string ;
  ] .

ex:SculptureShape a sh:NodeShape ;
  sh:targetClass ex:Sculpture ;

  sh:property [
    sh:path ex:hasSculptureMaterial ;
    sh:datatype xsd:string ;
  ] .
```

```
### Data graph ###
@prefix ex: <http://example.com/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .

###  http://example.com/david
ex:david rdf:type owl:NamedIndividual ,
                  ex:Sculpture ,
                  ex:Artefact ;
         ex:hasArtist ex:michelangelo ;
         ex:belongsToHistoricalMovement "Renaissance" ;
         ex:hasEndCreationDate 1504 ;
         ex:hasSculptureMaterial "Marble" ;
         ex:hasStartCreationDate 1501 ;
         rdfs:label "David" .


###  http://example.com/leonardo_da_vinci
ex:leonardo_da_vinci rdf:type owl:NamedIndividual ,
                              ex:Artist ;
                     rdfs:label "Leonardo Da Vinci" .


###  http://example.com/michelangelo
ex:michelangelo rdf:type owl:NamedIndividual ,
                         ex:Artist ;
                rdfs:label "Michelangelo" .


###  http://example.com/mona_lisa
ex:mona_lisa rdf:type owl:NamedIndividual ,
                      ex:Artefact ,
                      ex:Painting ;
             ex:hasArtist ex:leonardo_da_vinci ;
             ex:belongsToHistoricalMovement "Renaissance" ;
             ex:hasEndCreationDate 1517 ;
             ex:hasPaintType "Oil paint" ;
             ex:hasStartCreationDate 1503 ;
             rdfs:label "Mona Lisa" .


###  http://example.com/the_last_supper
ex:the_last_supper rdf:type owl:NamedIndividual ,
                            ex:Artefact ,
                            ex:Painting ;
                   ex:hasArtist ex:leonardo_da_vinci ;
                   ex:belongsToHistoricalMovement "Renaissance" ;
                   ex:hasEndCreationDate 1498 ;
                   ex:hasPaintType "Mural Paint" ;
                   ex:hasStartCreationDate 1494 ;
                   rdfs:label "The Last Supper" .
```

</div>

## Shape 5: [https://s.zazuko.com/w2YY1a](https://s.zazuko.com/w2YY1a){:target="\_blank"}

<div class="grid cards" markdown>

```
### SHACL shape ###
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

ex:PaintingShape a sh:NodeShape ;
  sh:targetClass ex:Painting ;

  sh:property [
    sh:path ex:hasPaintType ;
    sh:datatype xsd:string ;
  ] .

ex:SculptureShape a sh:NodeShape ;
  sh:targetClass ex:Sculpture ;

  sh:property [
    sh:path ex:hasSculptureMaterial ;
    sh:datatype xsd:string ;
  ] .
```

```
### Data graph ###
@prefix ex: <http://example.com/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .

ex:Painting rdfs:subClassOf ex:Artefact .
ex:Sculpture rdfs:subClassOf ex:Artefact .

ex:the_last_supper rdf:type ex:Painting ;
                   ex:hasArtist ex:leonardo_da_vinci ;
                   ex:belongsToHistoricalMovement "Renaissance" ;
                   ex:hasEndCreationDate 1498 ;
                   ex:hasPaintType "Mural Paint" ;
                   ex:hasStartCreationDate 1494 ;
                   rdfs:label "The Last Supper" .

ex:mona_lisa rdf:type ex:Painting ;
             ex:hasArtist ex:leonardo_da_vinci ;
             ex:belongsToHistoricalMovement "Renaissance" ;
             ex:hasEndCreationDate 1517 ;
             ex:hasPaintType "Oil paint" ;
             ex:hasStartCreationDate 1503 ;
             rdfs:label "Mona Lisa" .

ex:david rdf:type ex:Sculpture ;
         ex:hasArtist ex:michelangelo ;
         ex:belongsToHistoricalMovement "Renaissance" ;
         ex:hasEndCreationDate 1504 ;
         ex:hasSculptureMaterial "Marble" ;
         ex:hasStartCreationDate 1501 ;
         rdfs:label "David" .

ex:leonardo_da_vinci rdf:type ex:Artist ;
                     rdfs:label "Leonardo Da Vinci" .

ex:michelangelo rdf:type ex:Artist ;
                rdfs:label "Michelangelo" .
```

</div>

## Shape 6: [https://s.zazuko.com/uVBdkn](https://s.zazuko.com/uVBdkn){:target="\_blank"}

<div class="grid cards" markdown>

```
### SHACL shape ###
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

ex:PaintingShape a sh:NodeShape ;
  sh:targetClass ex:Painting ;
  sh:node ex:ArtefactShape ;

  sh:property [
    sh:path ex:hasPaintType ;
    sh:datatype xsd:string ;
  ] .

ex:SculptureShape a sh:NodeShape ;
  sh:targetClass ex:Sculpture ;
  sh:node ex:ArtefactShape ;

  sh:property [
    sh:path ex:hasSculptureMaterial ;
    sh:datatype xsd:string ;
  ] .
```

```
### Data graph ###
@prefix ex: <http://example.com/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .

ex:the_last_supper rdf:type ex:Painting ;
                   ex:hasArtist ex:leonardo_da_vinci ;
                   ex:belongsToHistoricalMovement "Renaissance" ;
                   ex:hasEndCreationDate 1498 ;
                   ex:hasPaintType "Mural Paint" ;
                   ex:hasStartCreationDate 1494 ;
                   rdfs:label "The Last Supper" .

ex:mona_lisa rdf:type ex:Painting ;
             ex:hasArtist ex:leonardo_da_vinci ;
             ex:belongsToHistoricalMovement "Renaissance" ;
             ex:hasEndCreationDate 1517 ;
             ex:hasPaintType "Oil paint" ;
             ex:hasStartCreationDate 1503 ;
             rdfs:label "Mona Lisa" .

ex:david rdf:type ex:Sculpture ;
         ex:hasArtist ex:michelangelo ;
         ex:belongsToHistoricalMovement "Renaissance" ;
         ex:hasEndCreationDate 1504 ;
         ex:hasSculptureMaterial "Marble" ;
         ex:hasStartCreationDate 1501 ;
         rdfs:label "David" .

ex:leonardo_da_vinci rdf:type ex:Artist ;
                     rdfs:label "Leonardo Da Vinci" .

ex:michelangelo rdf:type ex:Artist ;
                rdfs:label "Michelangelo" .
```

</div>

## Shape 7: [https://s.zazuko.com/2csFptb](https://s.zazuko.com/2csFptb){:target="\_blank"}

<div class="grid cards" markdown>

```
### SHACL shape ###
@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix ex: <http://example.com/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .

ex:ArtefactShape a sh:NodeShape ;
  sh:targetClass ex:Artefact ;
  sh:closed true ;
  sh:ignoredProperties (rdf:type rdfs:label) ;

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

ex:PaintingShape a sh:NodeShape ;
  sh:targetClass ex:Painting ;
  sh:node ex:ArtefactShape ;
  sh:closed true ;
  sh:ignoredProperties (rdf:type rdfs:label) ;

  sh:property [
    sh:path ex:hasPaintType ;
    sh:datatype xsd:string ;
  ] .

ex:SculptureShape a sh:NodeShape ;
  sh:targetClass ex:Sculpture ;
  sh:closed true ;
  sh:ignoredProperties (rdf:type rdfs:label) ;
  sh:node ex:ArtefactShape ;

  sh:property [
    sh:path ex:hasSculptureMaterial ;
    sh:datatype xsd:string ;
  ] .
```

```
### Data graph ###
@prefix ex: <http://example.com/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .

ex:Artefact a owl:Class .
ex:Painting rdfs:subClassOf ex:Artefact .
ex:Sculpture rdfs:subClassOf ex:Artefact .

ex:the_last_supper rdf:type ex:Painting ;
                   ex:hasArtist ex:leonardo_da_vinci ;
                   ex:belongsToHistoricalMovement "Renaissance" ;
                   ex:hasEndCreationDate 1498 ;
                   ex:hasPaintType "Mural Paint" ;
                   ex:hasStartCreationDate 1494 ;
                   rdfs:label "The Last Supper" .

ex:mona_lisa rdf:type ex:Painting ;
             ex:hasArtist ex:leonardo_da_vinci ;
             ex:belongsToHistoricalMovement "Renaissance" ;
             ex:hasEndCreationDate 1517 ;
             ex:hasPaintType "Oil paint" ;
             ex:hasStartCreationDate 1503 ;
             rdfs:label "Mona Lisa" .

ex:david rdf:type ex:Sculpture ;
         ex:hasArtist ex:michelangelo ;
         ex:belongsToHistoricalMovement "Renaissance" ;
         ex:hasEndCreationDate "1504" ;
         ex:hasSculptureMaterial "Marble" ;
         ex:hasStartCreationDate 1501 ;
         rdfs:label "David" .

ex:leonardo_da_vinci rdf:type ex:Artist ;
                     rdfs:label "Leonardo Da Vinci" .

ex:michelangelo rdf:type ex:Artist ;
                rdfs:label "Michelangelo" .
```

</div>

## Shape 8: [https://s.zazuko.com/31ZoAAz](https://s.zazuko.com/31ZoAAz){:target="\_blank"}

<div class="grid cards" markdown>

```
### SHACL shape ###
@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix ex: <http://example.com/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .

ex:ArtefactShape a sh:NodeShape ;
  sh:targetClass ex:Artefact ;
  sh:closed true ;
  sh:ignoredProperties (rdf:type rdfs:label) ;

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

ex:PaintingShape a sh:NodeShape ;
  sh:targetClass ex:Painting ;
  sh:node ex:ArtefactShape ;
  sh:closed true ;
  sh:ignoredProperties (rdf:type rdfs:label) ;

  sh:property [
    sh:path ex:hasPaintType ;
    sh:datatype xsd:string ;
  ] .

ex:SculptureShape a sh:NodeShape ;
  sh:targetClass ex:Sculpture ;
  sh:closed true ;
  sh:ignoredProperties (rdf:type rdfs:label) ;
  sh:node ex:ArtefactShape ;

  sh:property [
    sh:path ex:hasSculptureMaterial ;
    sh:datatype xsd:string ;
  ] .
```

```
### Data graph ###
@prefix ex: <http://example.com/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .

###  http://example.com/david
ex:david rdf:type owl:NamedIndividual ,
                  ex:Sculpture ,
                  ex:Artefact ;
         ex:hasArtist ex:michelangelo ;
         ex:belongsToHistoricalMovement "Renaissance" ;
         ex:hasEndCreationDate 1504 ;
         ex:hasSculptureMaterial "Marble" ;
         ex:hasStartCreationDate 1501 ;
         rdfs:label "David" .


###  http://example.com/leonardo_da_vinci
ex:leonardo_da_vinci rdf:type owl:NamedIndividual ,
                              ex:Artist ;
                     rdfs:label "Leonardo Da Vinci" .


###  http://example.com/michelangelo
ex:michelangelo rdf:type owl:NamedIndividual ,
                         ex:Artist ;
                rdfs:label "Michelangelo" .


###  http://example.com/mona_lisa
ex:mona_lisa rdf:type owl:NamedIndividual ,
                      ex:Artefact ,
                      ex:Painting ;
             ex:hasArtist ex:leonardo_da_vinci ;
             ex:belongsToHistoricalMovement "Renaissance" ;
             ex:hasEndCreationDate 1517 ;
             ex:hasPaintType "Oil paint" ;
             ex:hasStartCreationDate 1503 ;
             rdfs:label "Mona Lisa" .


###  http://example.com/the_last_supper
ex:the_last_supper rdf:type owl:NamedIndividual ,
                            ex:Artefact ,
                            ex:Painting ;
                   ex:hasArtist ex:leonardo_da_vinci ;
                   ex:belongsToHistoricalMovement "Renaissance" ;
                   ex:hasEndCreationDate 1498 ;
                   ex:hasPaintType "Mural Paint" ;
                   ex:hasStartCreationDate 1494 ;
                   rdfs:label "The Last Supper" .
```

</div>

## Shape 9: [https://s.zazuko.com/36xx2BC](https://s.zazuko.com/36xx2BC){:target="\_blank"}

<div class="grid cards" markdown>

```
### SHACL shape ###
@prefix sh: <http://www.w3.org/ns/shacl#> .
@prefix ex: <http://example.com/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .

ex:ArtefactShape a sh:NodeShape ;
  sh:targetClass ex:Artefact ;
  sh:closed true ;
  sh:ignoredProperties (rdf:type rdfs:label) ;

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

ex:PaintingShape a sh:NodeShape ;
  sh:targetClass ex:Painting ;
  sh:node ex:ArtefactShape ;
  sh:closed true ;
  sh:ignoredProperties (rdf:type rdfs:label) ;

  sh:property [
    sh:path ex:hasPaintType ;
    sh:datatype xsd:string ;
  ] .

ex:SculptureShape a sh:NodeShape ;
  sh:targetClass ex:Sculpture ;
  sh:closed true ;
  sh:ignoredProperties (rdf:type rdfs:label) ;
  sh:node ex:ArtefactShape ;

  sh:property [
    sh:path ex:hasSculptureMaterial ;
    sh:datatype xsd:string ;
  ] .
```

```
### Data graph ###
@prefix ex: <http://example.com/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .

ex:Artefact a owl:Class .
ex:Painting rdfs:subClassOf ex:Artefact .
ex:Sculpture rdfs:subClassOf ex:Artefact .

###  http://example.com/david
ex:david rdf:type owl:NamedIndividual ,
                  ex:Sculpture ,
                  ex:Artefact ;
         ex:hasArtist ex:michelangelo ;
         ex:belongsToHistoricalMovement "Renaissance" ;
         ex:hasEndCreationDate 1504 ;
         ex:hasSculptureMaterial "Marble" ;
         ex:hasStartCreationDate 1501 ;
         rdfs:label "David" .


###  http://example.com/leonardo_da_vinci
ex:leonardo_da_vinci rdf:type owl:NamedIndividual ,
                              ex:Artist ;
                     rdfs:label "Leonardo Da Vinci" .


###  http://example.com/michelangelo
ex:michelangelo rdf:type owl:NamedIndividual ,
                         ex:Artist ;
                rdfs:label "Michelangelo" .


###  http://example.com/mona_lisa
ex:mona_lisa rdf:type owl:NamedIndividual ,
                      ex:Artefact ,
                      ex:Painting ;
             ex:hasArtist ex:leonardo_da_vinci ;
             ex:belongsToHistoricalMovement "Renaissance" ;
             ex:hasEndCreationDate 1517 ;
             ex:hasPaintType "Oil paint" ;
             ex:hasStartCreationDate 1503 ;
             rdfs:label "Mona Lisa" .


###  http://example.com/the_last_supper
ex:the_last_supper rdf:type owl:NamedIndividual ,
                            ex:Artefact ,
                            ex:Painting ;
                   ex:hasArtist ex:leonardo_da_vinci ;
                   ex:belongsToHistoricalMovement "Renaissance" ;
                   ex:hasEndCreationDate 1498 ;
                   ex:hasPaintType "Mural Paint" ;
                   ex:hasStartCreationDate 1494 ;
                   rdfs:label "The Last Supper" .
```

</div>

## Shape 10: [](){:target="\_blank"}

<div class="grid cards" markdown>

```
### SHACL shape ###

```

```
### Data graph ###

```

</div>
