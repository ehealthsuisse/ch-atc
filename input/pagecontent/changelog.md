
All significant changes to this FHIR implementation guide will be documented on this page.   

### v3.3.0 (2024-12-18)

#### Open Issue
* 'Event Date and Time' in the Audit Events can no more be changed in this ballot [#42](https://github.com/ehealthsuisse/ch-atc/issues/42)

#### Added
* CapabilityStatement for the Patient Audit Record Repository [#47](https://github.com/ehealthsuisse/ch-atc/issues/47) 

#### Changed / Updated
* Revise [Introduction](https://fhir.ch/ig/ch-atc/index.html#introduction) [#23](https://github.com/ehealthsuisse/ch-atc/issues/23)
* Improve description of the exclusion of a healthcare professional from accessing an EPR [#25](https://github.com/ehealthsuisse/ch-atc/issues/25)
* Textual improvement of narrative part in examples [#26](https://github.com/ehealthsuisse/ch-atc/issues/26)
* Correct typo 'EPR_SPID' to 'EPR-SPID' in [Access Audit Trail Content Profile](https://fhir.ch/ig/ch-atc/volume-3.html#access-audit-trail-content-profile) [#27](https://github.com/ehealthsuisse/ch-atc/issues/27)
* Textual improvement in narrative part in example [#28](https://github.com/ehealthsuisse/ch-atc/issues/28)
* After adding the W3C Trace Context to this profile with [#18](https://github.com/ehealthsuisse/ch-atc/issues/18) remove it again from the descriptions and examples according to decision [#51](https://github.com/ehealthsuisse/ch-atc/issues/51)
* Correct reference from IHE 'ITI TF-1' to 'IHE ITI Supplement Add RESTful Query to ATNA' in [Patient Audit Record Repository](https://fhir.ch/ig/ch-atc/volume-1.html#patient-audit-record-repository) and [Patient Audit Consumer](https://fhir.ch/ig/ch-atc/volume-1.html#patient-audit-consumer) [#32](https://github.com/ehealthsuisse/ch-atc/issues/32), [#37](https://github.com/ehealthsuisse/ch-atc/issues/37)
* Add to the Aggregate Audit Message Option in [Integration Profile Options](https://fhir.ch/ig/ch-atc/volume-1.html#integration-profile-options) an OperationOutcome in case of a non-responding community [#33](https://github.com/ehealthsuisse/ch-atc/issues/33)
* Identifier in KeyElements table [#36](https://github.com/ehealthsuisse/ch-atc/issues/36) 
* CP 'EHSEPDBEP-244' XDSDocumentEntry.uniqueId precision [#38](https://github.com/ehealthsuisse/ch-atc/issues/38), [#53](https://github.com/ehealthsuisse/ch-atc/issues/53) 
* Correct example in [Security Considertations](https://fhir.ch/ig/ch-atc/volume-2.html#security-considerations) [#39](https://github.com/ehealthsuisse/ch-atc/issues/39)
* Remove 'user' from Additional ATNA Search Parameters [#40](https://github.com/ehealthsuisse/ch-atc/issues/40)
* Correct display name of the SNOMED CT code 419891008 [#43](https://github.com/ehealthsuisse/ch-atc/issues/43)
* Correct typo in reference to footnote [#44](https://github.com/ehealthsuisse/ch-atc/issues/44)
* Align min cardinalities in the ChAtcIti81Response profile [#48](https://github.com/ehealthsuisse/ch-atc/issues/48)
* Update the IG dependencies to the current published versions (HL7 Terminology 6.1.0, CH EPR FHIR 4.0.1-ballot-2)

#### Issues resolved without amendment (in IG)
* Remove Trace Context from CH ATC Profile [#51](https://github.com/ehealthsuisse/ch-atc/issues/51)

### v3.3.0-ballot (2024-05-17)

#### Added
* Integration of volume 1, 2 and 3 from 'Ergänzung 2.2 zu Anhang 5 EPDV-EDI' in consideration of CP 'EHSEPDBEP-244' [#12](https://github.com/ehealthsuisse/ch-atc/issues/12)
   * Add tracecontext by using ChEprFhirAuditEvent as parent profile for all AuditEvent profiles in CH ATC [#18](https://github.com/ehealthsuisse/ch-atc/issues/18)

#### Changed / Updated
* Updated the IG dependencies to the current published versions
   * Adapt VS URL (http://fhir.ch/ig/ch-epr/ValueSet/EprPurposeOfUse) because of renaming CH EPR Term to CH Term [#20](https://github.com/ehealthsuisse/ch-atc/issues/20)
* Change extension http://hl7.org/fhir/StructureDefinition/artifact-identifier to http://fhir.ch/ig/ch-epr-fhir/StructureDefinition/ch-mhd-home-community-id [#21](https://github.com/ehealthsuisse/ch-atc/issues/21)


### v3.2.0 (2024-01-31)
The implementation guide was under an informative ballot by HL7 Switzerland until September 30th, 2023. The following comments/issues have been raised and fixed:

#### Open Issues
* Overview of transactions/use cases [#12](https://github.com/ehealthsuisse/ch-atc/issues/12) 

#### Added
* [Example](Bundle-ch-atc-iti-81-response-sample.xml.html) for partial result in CH:ATC Query [#6](https://github.com/ehealthsuisse/ch-atc/issues/6)

#### Fixed
* Correct system for XDSDocumentEntry.uniqueId [#15](https://github.com/ehealthsuisse/ch-atc/issues/15) (raised in various comments [#7](https://github.com/ehealthsuisse/ch-atc/issues/7))
* Missing Feedback link, footer 3.2.0-ballot [#10](https://github.com/ehealthsuisse/ch-atc/issues/10), [#5](https://github.com/ehealthsuisse/ch-atc/issues/5)
* History page and naming, status [#9](https://github.com/ehealthsuisse/ch-atc/issues/9), [#11](https://github.com/ehealthsuisse/ch-atc/issues/11)  
* Partial Results [#6](https://github.com/ehealthsuisse/ch-atc/issues/6) 

### v3.2.0-ballot (2023-06-30)

#### Added
* Example for partial result in CH:ATC Query
* Added 'HpdAuditEvent' Profile and 'HpdAuditEventType' ValueSet.
   * Additional slice Bundle.entry:HpdAuditEvent in 'ChAtcIti81Response' profile.
* Added examples:
   * CH ATC - Audit Event for Document Search (Profile: DocumentAuditEvent)
   * CH ATC - Audit Event for Group Entry Audit Event Content Profile (Profile: HpdAuditEvent)
* Added 'STU Note' box, 'Change Log' and NPM package download link.

#### Changed / Updated
* DocumentAuditEvent:
   * Added slice AuditEvent.entity:Query
   * Added slice AuditEvent.entity:Document.detail:title
* Added the code 'ATC_DOC_SEARCH' to existing ValueSet 'DocumentAuditEventType'.
* Updated description of the 'ChAtcIti81Response' profile and unified the notation in the IG.
* Structural updates of the IG analogous to the further development of the IG Publisher. Removed elements in the differential which did not deviate from the core specification to clean the differential table of the profiles.
* Added an [example](Bundle-ch-atc-iti-81-response-sample.xml.html) how to indicate a partial success (e.g. one of the communities not responding)

#### Fixed
* Fixed URL of the SearchParameter: http://fhir.ch/ig/ch-atc/StructureDefinition/AuditEvent-entity-identifier -> http://fhir.ch/ig/ch-atc/SearchParameter/AuditEvent-entity-identifier
* Replaced invalid document type: birth certificate/radiology report -> record artifact
* Changed cardinalities:
   * DocumentAuditEvent: 
      * AuditEvent.entity: min 1 -> 0
* Fixed typos. 

### v3.1.0 (2020-06-11)
Updated draft version:
* Added SearchParameter 'AuditEvent entity.identifier'.
* Changed CodeSystem agentRole from 'urn:oid:2.16.756.5.30.1.127.3.10.8' to 'urn:oid:2.16.756.5.30.1.127.3.10.14'
* Introduction of dependence to implementation guide CH EPR Term.
   * Removed all CodeSystems.
   * Removed ValueSet 'EprPurposeOfUse'.
   * Adapted URLs of the ValueSets.
* Updated FHIR version from STU3 (v3.0.1) to R4 (v4.0.1).
* Structural updates of the IG analogous to the further development of the IG Publisher (e.g. new template).

### v1.2.0 (2019-03-01)
Initial published draft version according to 'www.e-health-suisse.ch/fileadmin/user_upload/Dokumente/2019/E/190528_Entwurf_EPDV-EDI_E2A5_ATC_V1.9_e.pdf'.