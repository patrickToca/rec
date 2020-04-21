# RealEstateCore Release Notes

## V3.1 -- Actuation Model

Version 3.1 is a feature release of REC that contains:

* The new Actuation module, with north- and southbound message semantics for enacting actuations on systems.
* Deprecation of the Room (Building module) and Premises (Lease module) type hierarchies, in favour of the RoomType and PremisesType classes, respectively. Named individuals of these classes are punned to the same IRIs as the now-deprecated classes, the latter of which will be removed in an upcoming 4.0 release.
* Documentation on REC recommendations for alignments with owl:sameAs and owl:equivalentClass (outside of ontology, see GitHub repo).
* Initial OWL2OAS annotations (work in progress, see https://github.com/hammar/owl2oas) governing how an OAS API will be generated from the REC OWL files. Will be fully functional by release 3.2.

## V3.0 -- Usability and maintainability refactoring

Version 3.0 is a major and compatibility-breaking refactoring of RealEstateCore. Emphasis in this release is not on development of new features, but rather on improved usability and maintainability in the long run. Changes include:

* All IRI:s are now HTTPS
* Properties have been defined as being (at-most) single-domain and single-range, supporting usability and visualization.
* Meronomy properties have been refactored to allow transitive traversal of the parthood hierarchy from RealEstate all the way down to individual devices using the isPartOf and hasPart superproperties.
  * This has required refactoring of the relations Building <-> BuildingComponent and Device <-> DeviceComponent (the latter is removed).
* Class naming has been simplified (BuildingStructure -> Building, BuildingStructureComponent -> BuildingComponent, etc).
* A (minimal) representation of GeoSPARQL has been integrated, to allow for standardized geospatial representations and querying. REC home-made geospatial/location vocabulary is phased out as a consequence.
* Alignments against other ontologies or standards (BIP, Belok, IPSO, Haystack, fi2xml, IFC) have been broken out into separate alignment files, and now use rdfs:seeAlso annotations.
* Module boundaries have been clarified and three new modules (Lease, Metadata, Agents) have been added, in preparation of anticipated modelling work.
* All entities have been assigned rdfs:labels and the large majority rdfs:comments.
* The modules have been documented with metadata using DC, CC, VANN, cpannotationschema, etc.
* Files have been renamed from .owl to .rdf, to simplify use in tools that expect this ending (e.g., TopBraid).

## 2.3 Actuation model

* Adds Actuation model (classes and properties)
* Extends room types (BuildingStructureComponent)
* Extends comparableCoClass mapping
* Adds example JSON-message
* Adds metrological QuantityKind:s
* Rename class DeviceFunction to DeviceFunctionType
* Extends range for object property serves
* Fixes varios typos

## 2.2 Initial public release

* The initial public release 2018-05-31. Contain the modules: Core, Building and Device.