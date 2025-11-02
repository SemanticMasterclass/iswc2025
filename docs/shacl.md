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

## Shape 10: [https://s.zazuko.com/V8M9tv](https://s.zazuko.com/V8M9tv){:target="\_blank"}

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
    sh:path ex:isOwnedBy ;
    sh:class ex:Owner ;
    sh:minCount 1 ;
    sh:maxCount 1 ;
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

ex:Artefact a owl:Class .
ex:Painting rdfs:subClassOf ex:Artefact .
ex:Sculpture rdfs:subClassOf ex:Artefact .

ex:the_last_supper rdf:type ex:Painting ;
                   ex:hasArtist ex:leonardo_da_vinci ;
                   ex:belongsToHistoricalMovement "Renaissance" ;
                   ex:hasEndCreationDate 1498 ;
                   ex:hasPaintType "Mural Paint" ;
                   ex:hasStartCreationDate 1494 ;
				   ex:isOwnedBy ex:davide ;
                   rdfs:label "The Last Supper" .

ex:mona_lisa rdf:type ex:Painting ;
             ex:hasArtist ex:leonardo_da_vinci ;
             ex:belongsToHistoricalMovement "Renaissance" ;
             ex:hasEndCreationDate 1517 ;
             ex:hasPaintType "Oil paint" ;
             ex:hasStartCreationDate 1503 ;
             ex:isOwnedBy ex:tara ;
             rdfs:label "Mona Lisa" .

ex:david rdf:type ex:Sculpture ;
         ex:hasArtist ex:michelangelo ;
         ex:belongsToHistoricalMovement "Renaissance" ;
         ex:hasEndCreationDate 1504 ;
         ex:hasSculptureMaterial "Marble" ;
         ex:hasStartCreationDate 1501 ;
         ex:isOwnedBy ex:tara ;
         rdfs:label "David" .

ex:leonardo_da_vinci rdf:type ex:Artist ;
                     rdfs:label "Leonardo Da Vinci" .

ex:michelangelo rdf:type ex:Artist ;
                rdfs:label "Michelangelo" .

ex:davide a ex:Owner ;
	rdfs:label "Davide" .

ex:tara a ex:Owner ;
	rdfs:label "Tara" .
```

</div>

## Shape 11: [https://s.zazuko.com/3zXqWN1](https://s.zazuko.com/3zXqWN1){:target="\_blank"}

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
         ex:hasEndCreationDate 1504 ;
         ex:hasSculptureMaterial "Marble" ;
         ex:hasStartCreationDate 1501 ;
         ex:isOwnedBy ex:tara ;
         rdfs:label "David" .

ex:leonardo_da_vinci rdf:type ex:Artist ;
                     rdfs:label "Leonardo Da Vinci" .

ex:michelangelo rdf:type ex:Artist ;
                rdfs:label "Michelangelo" .
```

</div>

## Shape 12: [Link](https://shacl-playground.zazuko.com/#shapesGraph=%40prefix+sh%3A+%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fshacl%23%3E+.%0A%40prefix+ex%3A+%3Chttp%3A%2F%2Fexample.com%2F%3E+.%0A%40prefix+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E+.%0A%40prefix+xsd%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2001%2FXMLSchema%23%3E+.%0A%40prefix+rdf%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F1999%2F02%2F22-rdf-syntax-ns%23%3E+.%0A%40prefix+xsd%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2001%2FXMLSchema%23%3E+.%0A%40prefix+owl%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E+.%0A%0Aex%3AArtefactShape+a+sh%3ANodeShape+%3B%0A++sh%3AtargetClass+ex%3AArtefact+%3B%0A%0A++sh%3Aproperty+%5B%0A++++sh%3Apath+ex%3AbelongsToHistoricalMovement+%3B%0A++++sh%3Aclass+ex%3AMovement+%3B%0A++%5D+%3B++++%0A%0A++sh%3Aproperty+%5B%0A++++sh%3Apath+ex%3AhasArtist+%3B%0A++++sh%3Aclass+ex%3AArtist+%3B%0A++%5D+%3B%0A%0A++sh%3Aproperty+%5B%0A++++sh%3Apath+ex%3AhasEndCreationDate+%3B%0A++++sh%3Adatatype+xsd%3Ainteger+%3B%0A++++sh%3AminCount+1+%3B%0A++++sh%3AmaxCount+1+%3B%0A++%5D+%3B%0A%0A++sh%3Aproperty+%5B%0A++++sh%3Apath+ex%3AhasStartCreationDate+%3B%0A++++sh%3Adatatype+xsd%3Ainteger+%3B%0A++++sh%3AminCount+1+%3B%0A++++sh%3AmaxCount+1+%3B%0A++%5D+.%0A%0Aex%3APaintingShape+a+sh%3ANodeShape+%3B%0A++sh%3AtargetClass+ex%3APainting+%3B%0A++sh%3Anode+ex%3AArtefactShape+%3B%0A%0A++sh%3Aproperty+%5B%0A++++sh%3Apath+ex%3AhasPaintType+%3B%0A++++sh%3Adatatype+xsd%3Astring+%3B%0A++%5D+.%0A%0Aex%3ASculptureShape+a+sh%3ANodeShape+%3B%0A++sh%3AtargetClass+ex%3ASculpture+%3B%0A++sh%3Anode+ex%3AArtefactShape+%3B%0A%0A++sh%3Aproperty+%5B%0A++++sh%3Apath+ex%3AhasSculptureMaterial+%3B%0A++++sh%3Adatatype+xsd%3Astring+%3B%0A++%5D+.%0A&dataGraph=%40prefix+ex%3A+%3Chttp%3A%2F%2Fexample.com%2F%3E+.%0A%40prefix+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E+.%0A%40prefix+xsd%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2001%2FXMLSchema%23%3E+.%0A%40prefix+rdf%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F1999%2F02%2F22-rdf-syntax-ns%23%3E+.%0A%40prefix+xsd%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2001%2FXMLSchema%23%3E+.%0A%40prefix+owl%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E+.%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Fcubism%0Aex%3Acubism+rdf%3Atype+owl%3ANamedIndividual+%2C%0A+++++++++++++++++++ex%3AMovement+%3B%0A++++++++++ex%3AhasEndDate+1940+%3B%0A++++++++++ex%3AhasStartDate+1900+%3B%0A++++++++++rdfs%3Alabel+%22Cubism%22+.%0A%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Fdavid%0Aex%3Adavid+rdf%3Atype+owl%3ANamedIndividual+%2C%0A++++++++++++++++++ex%3ASculpture+%3B%0A+++++++++ex%3AbelongsToHistoricalMovement+ex%3Arenaissance+%3B%0A+++++++++ex%3AhasArtist+ex%3Amichelangelo+%3B%0A+++++++++ex%3AhasEndCreationDate+1504+%3B%0A+++++++++ex%3AhasSculptureMaterial+%22Marble%22+%3B%0A+++++++++ex%3AhasStartCreationDate+1501+%3B%0A+++++++++rdfs%3Alabel+%22David%22+.%0A%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Fedvard_munch%0Aex%3Aedvard_munch+rdf%3Atype+owl%3ANamedIndividual+%2C%0A+++++++++++++++++++++++++ex%3AArtist+%3B%0A++++++++++++++++rdfs%3Alabel+%22Edvard+Munch%22+.%0A%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Fexpressionism%0Aex%3Aexpressionism+rdf%3Atype+owl%3ANamedIndividual+%2C%0A++++++++++++++++++++++++++ex%3AMovement+%3B%0A+++++++++++++++++ex%3AhasEndDate+1910+%3B%0A+++++++++++++++++ex%3AhasStartDate+1890+%3B%0A+++++++++++++++++rdfs%3Alabel+%22Expressionism%22+.%0A%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Fleonardo_da_vinci%0Aex%3Aleonardo_da_vinci+rdf%3Atype+owl%3ANamedIndividual+%2C%0A++++++++++++++++++++++++++++++ex%3AArtist+%3B%0A+++++++++++++++++++++rdfs%3Alabel+%22Leonardo+Da+Vinci%22+.%0A%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Fmichelangelo%0Aex%3Amichelangelo+rdf%3Atype+owl%3ANamedIndividual+%2C%0A+++++++++++++++++++++++++ex%3AArtist+%3B%0A++++++++++++++++rdfs%3Alabel+%22Michelangelo%22+.%0A%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Fmona_lisa%0Aex%3Amona_lisa+rdf%3Atype+owl%3ANamedIndividual+%2C%0A++++++++++++++++++++++ex%3APainting+%3B%0A+++++++++++++ex%3AbelongsToHistoricalMovement+ex%3Arenaissance+%3B%0A+++++++++++++ex%3AhasArtist+ex%3Aleonardo_da_vinci+%3B%0A+++++++++++++ex%3AhasEndCreationDate+1517+%3B%0A+++++++++++++ex%3AhasPaintType+%22Oil+paint%22+%3B%0A+++++++++++++ex%3AhasStartCreationDate+1503+%3B%0A+++++++++++++rdfs%3Alabel+%22Mona+Lisa%22+.%0A%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Fpablo_picasso%0Aex%3Apablo_picasso+rdf%3Atype+owl%3ANamedIndividual+%2C%0A++++++++++++++++++++++++++ex%3AArtist+%3B%0A+++++++++++++++++rdfs%3Alabel+%22Pablo+Picasso%22+.%0A%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Frenaissance%0Aex%3Arenaissance+rdf%3Atype+owl%3ANamedIndividual+%2C%0A++++++++++++++++++++++++ex%3AMovement+%3B%0A+++++++++++++++ex%3AhasEndDate+1600+%3B%0A+++++++++++++++ex%3AhasStartDate+1401+%3B%0A+++++++++++++++rdfs%3Alabel+%22Renaissance%22+.%0A%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Fsandro_botticelli%0Aex%3Asandro_botticelli+rdf%3Atype+owl%3ANamedIndividual+%2C%0A++++++++++++++++++++++++++++++ex%3AArtist+%3B%0A+++++++++++++++++++++rdfs%3Alabel+%22Sandro+Botticelli%22+.%0A%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Fthe_birth_of_venus%0Aex%3Athe_birth_of_venus+rdf%3Atype+owl%3ANamedIndividual+%2C%0A+++++++++++++++++++++++++++++++ex%3APainting+%3B%0A++++++++++++++++++++++ex%3AbelongsToHistoricalMovement+ex%3Arenaissance+%3B%0A++++++++++++++++++++++ex%3AhasArtist+ex%3Asandro_botticelli+%3B%0A++++++++++++++++++++++ex%3AhasEndCreationDate+1486+%3B%0A++++++++++++++++++++++ex%3AhasStartCreationDate+1484+%3B%0A++++++++++++++++++++++rdfs%3Alabel+%22The+Birth+of+Venus%22+.%0A%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Fthe_last_supper%0Aex%3Athe_last_supper+rdf%3Atype+owl%3ANamedIndividual+%2C%0A++++++++++++++++++++++++++++ex%3APainting+%3B%0A+++++++++++++++++++ex%3AbelongsToHistoricalMovement+ex%3Arenaissance+%3B%0A+++++++++++++++++++ex%3AhasArtist+ex%3Aleonardo_da_vinci+%3B%0A+++++++++++++++++++ex%3AhasEndCreationDate+1498+%3B%0A+++++++++++++++++++ex%3AhasPaintType+%22Mural+Paint%22+%3B%0A+++++++++++++++++++ex%3AhasStartCreationDate+1494+%3B%0A+++++++++++++++++++rdfs%3Alabel+%22The+Last+Supper%22+.%0A%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Fthe_scream%0Aex%3Athe_scream+rdf%3Atype+owl%3ANamedIndividual+%2C%0A+++++++++++++++++++++++ex%3APainting+%3B%0A++++++++++++++ex%3AbelongsToHistoricalMovement+ex%3Aexpressionism+%3B%0A++++++++++++++ex%3AhasArtist+ex%3Aedvard_munch+%3B%0A++++++++++++++ex%3AhasEndCreationDate+1893+%3B%0A++++++++++++++ex%3AhasStartCreationDate+1893+%3B%0A++++++++++++++rdfs%3Alabel+%22The+Scream%22+.%0A%0A%0A%23%23%23++http%3A%2F%2Fexample.com%2Fweeping_woman%0Aex%3Aweeping_woman+rdf%3Atype+owl%3ANamedIndividual+%2C%0A++++++++++++++++++++++++++ex%3APainting+%3B%0A+++++++++++++++++ex%3AbelongsToHistoricalMovement+ex%3Acubism+%3B%0A+++++++++++++++++ex%3AhasArtist+ex%3Apablo_picasso+%3B%0A+++++++++++++++++ex%3AhasEndCreationDate+1937+%3B%0A+++++++++++++++++ex%3AhasStartCreationDate+1937+%3B%0A+++++++++++++++++rdfs%3Alabel+%22Weeping+Woman%22+.&shapesGraphFormat=text%2Fturtle&dataGraphFormat=text%2Fturtle){:target="\_blank"}

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
    sh:class ex:Movement ;
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

###  http://example.com/cubism
ex:cubism rdf:type owl:NamedIndividual ,
                   ex:Movement ;
          ex:hasEndDate 1940 ;
          ex:hasStartDate 1900 ;
          rdfs:label "Cubism" .


###  http://example.com/david
ex:david rdf:type owl:NamedIndividual ,
                  ex:Sculpture ;
         ex:belongsToHistoricalMovement ex:renaissance ;
         ex:hasArtist ex:michelangelo ;
         ex:hasEndCreationDate 1504 ;
         ex:hasSculptureMaterial "Marble" ;
         ex:hasStartCreationDate 1501 ;
         rdfs:label "David" .


###  http://example.com/edvard_munch
ex:edvard_munch rdf:type owl:NamedIndividual ,
                         ex:Artist ;
                rdfs:label "Edvard Munch" .


###  http://example.com/expressionism
ex:expressionism rdf:type owl:NamedIndividual ,
                          ex:Movement ;
                 ex:hasEndDate 1910 ;
                 ex:hasStartDate 1890 ;
                 rdfs:label "Expressionism" .


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
                      ex:Painting ;
             ex:belongsToHistoricalMovement ex:renaissance ;
             ex:hasArtist ex:leonardo_da_vinci ;
             ex:hasEndCreationDate 1517 ;
             ex:hasPaintType "Oil paint" ;
             ex:hasStartCreationDate 1503 ;
             rdfs:label "Mona Lisa" .


###  http://example.com/pablo_picasso
ex:pablo_picasso rdf:type owl:NamedIndividual ,
                          ex:Artist ;
                 rdfs:label "Pablo Picasso" .


###  http://example.com/renaissance
ex:renaissance rdf:type owl:NamedIndividual ,
                        ex:Movement ;
               ex:hasEndDate 1600 ;
               ex:hasStartDate 1401 ;
               rdfs:label "Renaissance" .


###  http://example.com/sandro_botticelli
ex:sandro_botticelli rdf:type owl:NamedIndividual ,
                              ex:Artist ;
                     rdfs:label "Sandro Botticelli" .


###  http://example.com/the_birth_of_venus
ex:the_birth_of_venus rdf:type owl:NamedIndividual ,
                               ex:Painting ;
                      ex:belongsToHistoricalMovement ex:renaissance ;
                      ex:hasArtist ex:sandro_botticelli ;
                      ex:hasEndCreationDate 1486 ;
                      ex:hasStartCreationDate 1484 ;
                      rdfs:label "The Birth of Venus" .


###  http://example.com/the_last_supper
ex:the_last_supper rdf:type owl:NamedIndividual ,
                            ex:Painting ;
                   ex:belongsToHistoricalMovement ex:renaissance ;
                   ex:hasArtist ex:leonardo_da_vinci ;
                   ex:hasEndCreationDate 1498 ;
                   ex:hasPaintType "Mural Paint" ;
                   ex:hasStartCreationDate 1494 ;
                   rdfs:label "The Last Supper" .


###  http://example.com/the_scream
ex:the_scream rdf:type owl:NamedIndividual ,
                       ex:Painting ;
              ex:belongsToHistoricalMovement ex:expressionism ;
              ex:hasArtist ex:edvard_munch ;
              ex:hasEndCreationDate 1893 ;
              ex:hasStartCreationDate 1893 ;
              rdfs:label "The Scream" .


###  http://example.com/weeping_woman
ex:weeping_woman rdf:type owl:NamedIndividual ,
                          ex:Painting ;
                 ex:belongsToHistoricalMovement ex:cubism ;
                 ex:hasArtist ex:pablo_picasso ;
                 ex:hasEndCreationDate 1937 ;
                 ex:hasStartCreationDate 1937 ;
                 rdfs:label "Weeping Woman" .
```

</div>

## Shape 13: [https://s.zazuko.com/2Yg4EBo](https://s.zazuko.com/2Yg4EBo){:target="\_blank"}

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
    sh:class ex:Movement ;
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
    sh:class ex:PaintType ;
    sh:in (ex:oil_paint ex:mural_paint ex:tempera) ;
  ] .

ex:SculptureShape a sh:NodeShape ;
  sh:targetClass ex:Sculpture ;
  sh:node ex:ArtefactShape ;

  sh:property [
    sh:path ex:hasSculptureMaterial ;
    sh:class ex:SculptureMaterial ;
    sh:in (ex:marble ex:bronze) ;
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

ex:bronze rdf:type ex:SculptureMaterial ;
          rdfs:label "Bronze" .

ex:cubism rdf:type ex:Movement ;
          ex:hasEndDate 1940 ;
          ex:hasStartDate 1900 ;
          rdfs:label "Cubism" .

ex:david rdf:type ex:Sculpture ;
         ex:belongsToHistoricalMovement ex:renaissance ;
         ex:hasArtist ex:michelangelo ;
         ex:hasSculptureMaterial ex:marble ;
         ex:isExhibitedIn ex:gallery_of_the_academy_florence ;
         ex:isLocatedIn ex:florence ,
                        ex:italy ;
         ex:hasEndCreationDate 1504 ;
         ex:hasStartCreationDate 1501 ;
         rdfs:label "David" .

ex:edvard_munch rdf:type ex:Artist ;
                ex:belongsToHistoricalMovement ex:expressionism ;
                ex:isArtistOf ex:the_scream ;
                rdfs:label "Edvard Munch" .

ex:expressionism rdf:type owl:NamedIndividual ,
                          ex:Movement ;
                 ex:hasEndDate 1910 ;
                 ex:hasStartDate 1890 ;
                 rdfs:label "Expressionism" .

ex:florence rdf:type ex:City ;
            ex:isLocatedIn ex:italy ;
            rdfs:label "Florence" .

ex:fresco rdf:type owl:NamedIndividual ;
          rdfs:label "Fresco" .

ex:gallery_of_the_academy_florence rdf:type ex:Premises ;
                                   ex:isLocatedIn ex:florence ,
                                                  ex:italy ;
                                   rdfs:label "Gallery of the Academy of Florence" .

ex:italy rdf:type ex:Country ;
         rdfs:label "Italy" .

ex:leonardo_da_vinci rdf:type ex:Artist ;
                     ex:belongsToHistoricalMovement ex:renaissance ;
                     ex:isArtistOf ex:mona_lisa ,
                                   ex:the_last_supper ;
                     rdfs:label "Leonardo Da Vinci" .

ex:marble rdf:type ex:SculptureMaterial ;
          rdfs:label "Marble" .

ex:michelangelo rdf:type ex:Artist ;
                ex:belongsToHistoricalMovement ex:renaissance ;
                ex:isArtistOf ex:david ;
                rdfs:label "Michelangelo" .

ex:milan rdf:type ex:City ;
         ex:isLocatedIn ex:italy ;
         rdfs:label "Milan" .

ex:mona_lisa rdf:type ex:Painting ;
             ex:belongsToHistoricalMovement ex:renaissance ;
             ex:hasArtist ex:leonardo_da_vinci ;
             ex:hasPaintType ex:oil_paint ;
             ex:hasEndCreationDate 1517 ;
             ex:hasStartCreationDate 1503 ;
             rdfs:label "Mona Lisa" .

ex:mural_paint rdf:type ex:PaintType ;
               rdfs:label "Mural paint" .

ex:oil_paint rdf:type ex:PaintType ;
             rdfs:label "Oil paint" .

ex:pablo_picasso rdf:type ex:Artist ;
                 ex:belongsToHistoricalMovement ex:cubism ;
                 ex:isArtistOf ex:weeping_woman ;
                 rdfs:label "Pablo Picasso" .

ex:renaissance rdf:type ex:Movement ;
               ex:hasEndDate 1600 ;
               ex:hasStartDate 1401 ;
               rdfs:label "Renaissance" .

ex:sandro_botticelli rdf:type ex:Artist ;
                     ex:belongsToHistoricalMovement ex:renaissance ;
                     ex:isArtistOf ex:the_birth_of_venus ;
                     rdfs:label "Sandro Botticelli" .

ex:santa_maria_delle_grazie rdf:type ex:Premises ;
                            ex:isLocatedIn ex:italy ,
                                           ex:milan ;
                            rdfs:label "Santa Maria delle Grazie" .

ex:tempera rdf:type ex:PaintType ;
           rdfs:label "Tempera" .

ex:the_birth_of_venus rdf:type ex:Painting ;
                      ex:belongsToHistoricalMovement ex:renaissance ;
                      ex:hasArtist ex:sandro_botticelli ;
                      ex:hasPaintType ex:tempera ;
                      ex:isExhibitedIn ex:uffizi_gallery ;
                      ex:isLocatedIn ex:florence ,
                                     ex:italy ;
                      ex:hasEndCreationDate 1486 ;
                      ex:hasStartCreationDate 1484 ;
                      rdfs:label "The Birth of Venus" .

ex:the_last_supper rdf:type ex:Painting ;
                   ex:belongsToHistoricalMovement ex:renaissance ;
                   ex:hasArtist ex:leonardo_da_vinci ;
                   ex:hasPaintType ex:mural_paint ;
                   ex:isExhibitedIn ex:santa_maria_delle_grazie ;
                   ex:isLocatedIn ex:italy ,
                                  ex:milan ;
                   ex:hasEndCreationDate 1498 ;
                   ex:hasStartCreationDate 1494 ;
                   rdfs:label "The Last Supper" .

ex:the_scream rdf:type ex:Painting ;
              ex:belongsToHistoricalMovement ex:expressionism ;
              ex:hasArtist ex:edvard_munch ;
              ex:hasPaintType ex:oil_paint ;
              ex:hasEndCreationDate 1893 ;
              ex:hasStartCreationDate 1893 ;
              rdfs:label "The Scream" .

ex:uffizi_gallery rdf:type ex:Premises ;
                  ex:isLocatedIn ex:florence ,
                                 ex:italy ;
                  rdfs:label "Uffizi Gallery" .

ex:weeping_woman rdf:type ex:Painting ;
                 ex:belongsToHistoricalMovement ex:cubism ;
                 ex:hasArtist ex:pablo_picasso ;
                 ex:hasPaintType ex:oil_paint ;
                 ex:hasEndCreationDate 1937 ;
                 ex:hasStartCreationDate 1937 ;
                 rdfs:label "Weeping Woman" .
```

</div>
