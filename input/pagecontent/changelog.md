
All significant changes to this FHIR implementation guide will be documented on this page.   

### v3.3.0-ballot (2024)

#### Added
* Integration of volume 1, 2 and 3 from 'Ergänzung 2.2 zu Anhang 5 EPDV-EDI' in consideration of CP 'EPDBEP-244' [#12](https://github.com/ehealthsuisse/ch-atc/issues/12)


#### Changed / Updated
* Updated the IG dependencies to the current published versions
   * Adapt VS URL (http://fhir.ch/ig/ch-epr/ValueSet/EprPurposeOfUse) because of renaming CH EPR Term to CH Term [#20](https://github.com/ehealthsuisse/ch-atc/issues/20)

### v3.2.0 (2024-01-31)
The implementation guide was under an informative ballot by HL7 Switzerland until September 30th, 2023. The following comments/issues have been raised and fixed:

#### Open
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
Initial published draft version according to 'www.e-health-suisse.ch/fileadmin/user_upload/Dokumente/2019/E/190528_Entwurf_EPDV-EDI_E2A5_ATC_V1.9_e.pdf' (see on [e-health-suisse.ch](https://www.e-health-suisse.ch/beispielseiten/epd-projectathon/programmierhilfen-epd/relevante-spezifikationen.html#ATC)).