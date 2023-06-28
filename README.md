# Auroral Core Ontology V2

This repository contains the code and documentation generated for the the AURORAL Core ontology V2 (Dataset entity added).

## Current version of the ontology model with the Dataset entity added

![core](https://github.com/morelab/auroral-core-ontology-v2/blob/master/diagrams/core-dataset.png)

# Lines added to the ontology file

@prefix dcat: <http://www.w3.org/ns/dcat#> .

<https://auroral.iot.linkeddata.es/def/core#> rdf:type owl:Ontology ;
                                               dc:creator "Ahlem Rhayem" ,
                                                          "Alba Fernández Izquierdo" ,
                                                          "Andrea Cimmino" ,
                                                          "María Poveda-Villalón" ,
                                                          "Raúl García Castro" ;
                                               dc:contributor "David Buján-Carballal" ;
                                               dc:description "This ontology aims at modelling the data related to users, items, notification and organisations for the AURORAL project." ;
                                               dc:title "The AURORAL Core Ontology" ;
                                               <http://purl.org/dc/terms/license> <http://purl.org/NET/rdflicense/cc-by4.0> ;
                                               owl:versionInfo "0.0.3" .



#################################################################
#    Annotation properties
#################################################################

###  http://purl.org/dc/elements/1.1/contributor
dc:contributor rdf:type owl:AnnotationProperty .

###  http://purl.org/dc/elements/1.1/description
dc:description rdf:type owl:AnnotationProperty .

###  http://purl.org/dc/elements/1.1/title
dc:title rdf:type owl:AnnotationProperty .

###  http://purl.org/dc/terms/license
<http://purl.org/dc/terms/license> rdf:type owl:AnnotationProperty .



#################################################################
#    Data properties
#################################################################

###  http://purl.org/dc/elements/1.1/license
dc:license rdf:type owl:DatatypeProperty .


###  http://www.w3.org/ns/dcat#accessURL
dcat:accessURL rdf:type owl:DatatypeProperty .


###  http://www.w3.org/ns/dcat#keyword
dcat:keyword rdf:type owl:DatatypeProperty .



	#################################################################
#    Classes
#################################################################

###  http://www.w3.org/ns/dcat#Dataset
dcat:Dataset rdf:type owl:Class ;
             rdfs:label "Dataset" .

###  https://auroral.iot.linkeddata.es/def/core#Dataset
core:Dataset rdf:type owl:Class ;
             rdfs:subClassOf dcat:Dataset ,
                             core:VirtualThing ,
                             [ rdf:type owl:Restriction ;
                               owl:onProperty core:hasDomain ;
                               owl:allValuesFrom core:Domain
                             ] ,
                             [ rdf:type owl:Restriction ;
                               owl:onProperty core:provider ;
                               owl:allValuesFrom core:Organisation
                             ] ,
                             [ rdf:type owl:Restriction ;
                               owl:onProperty dc:description ;
                               owl:someValuesFrom xsd:string
                             ] ,
                             [ rdf:type owl:Restriction ;
                               owl:onProperty dc:license ;
                               owl:someValuesFrom xsd:string
                             ] ,
                             [ rdf:type owl:Restriction ;
                               owl:onProperty dc:title ;
                               owl:someValuesFrom xsd:string
                             ] ,
                             [ rdf:type owl:Restriction ;
                               owl:onProperty dcat:accessURL ;
                               owl:someValuesFrom xsd:string
                             ] ,
                             [ rdf:type owl:Restriction ;
                               owl:onProperty dcat:keyword ;
                               owl:someValuesFrom xsd:string
                             ] ,
                             [ rdf:type owl:Restriction ;
                               owl:onProperty core:visibility ;
                               owl:someValuesFrom xsd:boolean
                             ] ;
             rdfs:label "Dataset" .