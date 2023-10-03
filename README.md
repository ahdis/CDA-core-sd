## FHIR Logical Models for CDA

The `input` directory contains FHIR artifacts representing the core CDA logic models (in StructureDefinition resources).
The FHIR logical models for CDA are currently in development and do not yet include all approved CDA/SDTC extensions. It is the goal to eventually have all approved extensions represented in the FHIR logical models for CDA, at which point the two sets of artifacts will be aligned. Until this time, releases within this repository will include FHIR logical models for CDA that do not perfectly represent the CDA schema in the release.

Files/folders related to the FHIR logical models:
* input/
* input-cache/
* _updatePublisher.bat
* ig.ini
* publish.bat


## CDA Schema

The original (normative) schema and update schema with extensions is maintained at https://github.com/HL7/CDA-core-2.0.

### CDA Stylesheet

The CDA Stylesheet is located [here](https://github.com/HL7/cda-core-xsl). It is currently being managed by Alex Henket for SDWG.



### model updates in matchbox branch


#### IHE LAB and Pharm additions
LabCriterion.xml
LabPrecondition.xml
Material.xml
ObservationRange.xml
Person.xml
PharmContent.xml
PharmIngredient.xml
PharmMedicineClass.xml
PharmPackagedMedicine.xml
PharmSpecializedKind.xml
PharmSubstance.xml
PharmSuperContent.xml
ServiceEvent.xml


#### Versionless dependeny to terminology
ValueSet/CDAAddressUse.xml
ValueSet/CDACompressionAlgorithm.xml
ValueSet/CDAEntityNameUse.xml
ValueSet/CDANullFlavor.xml
ValueSet/CDAPostalAddressUse.xml
ValueSet/CDASignatureCode.xml

#### Australian addition
CS Support in Observation.value

#### Austria additions

ClinicalDocument
ELGA hl7at extension: ClinicalDocument.terminologyDate
ELGA hl7at extension: ClinicalDocument.formatCode
ELGA hl7at extension: ClinicalDocument.practiceSettingCode
ELGA changed from 1 to * ClinicalDocument.legalAuthenticator
ELGA changed from 1 to * CustodianOrganization.telecom

##### changes from at model
Act.precondition2 -> Act.sdtcPrecondition2
Act.inFulfillmentOf1 -> Act.sdtcInFulfillmentOf1
POCD_MT000040.InfrastructureRoot.typeId -> alread integrated in the new model
ClinicalDocument.classCode -> optional but fixed code
ClinicalDocument.statusCode -> ClinicalDocument.sdtcStatusCode
Encounter.precondition2 -> sdtcPrecondition2
Encounter.inFulfillmentOf1 -> sdtcInFulfillmentOf1
Procedure.precondition2 -> Procedure.sdtcPrecondition2
Procedure.inFulfillmentOf1 -> sdtcInFulfillmentOf1
Encounter.classCode -> not more  more restrictive than schema
AlternateIdentification.id TODO ELGA - why not sdtc at this point? Compare to IdentifiedBy.xml 
Component2 -> Component

cda elements which have choice groups have an an additional item element in the logical model, this is applicable for AD, EN, PN and (derived), StructureMap need to be adapted (http://hl7.org/fhir/tools/StructureDefinition/xml-choice-group)