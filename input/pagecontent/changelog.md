
All significant changes to this FHIR implementation guide will be documented on this page.   

### vx.x.x (2022-xx-xx)


#### Added
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

#### Fixed
* Fixed URL of the SearchParameter: http://fhir.ch/ig/ch-atc/StructureDefinition/AuditEvent-entity-identifier -> http://fhir.ch/ig/ch-atc/SearchParameter/AuditEvent-entity-identifier
* Replaced invalid document type: birth certificate/radiology report -> record artifcat
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