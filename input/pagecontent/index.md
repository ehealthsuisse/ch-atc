### Introduction

**TODO** -> IG Text bisher:    
This profile defines the audit trail consumption requirements a community has to provide for a patient. The profile CH ATC defines and precises the actors and transaction [ITI-81] of the [IHE IT Infrastructure Technical Framework Supplement Add RESTful Query to ATNA](https://www.ihe.net/uploadedFiles/Documents/ITI/IHE_ITI_Suppl_RESTful-ATNA.pdf) and defines the content of the Audit Messages. The different types of the Audit Messages are based on the requirements for Document and Policy Access management in order to achieve the Swiss regulation needs on the audit trail access by patients. These Audit Event types differ from the Audit Events which have also to be logged according to the IHE / CH:ATNA requirements.

The CH ATC profile text in the National Integration Profiles (SR816.11, Annex 5, Extension 2) is normative, this implementation guide is informative. This implementation guide is built with [IG Publisher](https://confluence.hl7.org/display/FHIR/IG+Publisher+Documentation) from HL7. See [e-health-suisse.ch](https://www.e-health-suisse.ch/startseite.html) for more information about the Electronic Patient Record in Switzerland.

**TODO** -> Text aus Word neu:    
This document fulfils the Swiss regulations of the Ordinance on the Electronic Patient Record (EPRO, SR 816.11). The EPRO and the EPRO-FDHA (SR 816.111) are published in Official Compilation of Federal Legislation (available in [German](https://www.admin.ch/opc/de/classified-compilation/20111795/index.html), [French](https://www.admin.ch/opc/fr/classified-compilation/20111795/index.html) and [Italian](https://www.admin.ch/opc/it/classified-compilation/20111795/index.html)).
The Swiss Electronic Health Record (EPR) depends on an IHE XDS and multi-community based system where the patient not only consents to the creation and use of the record, but does so by explicitly defining access rules through a patient portal.
Patients – and, if existing, their representatives – have the right to access the audit trail within the EPR circle of trust. The access to the audit trail will be provided by certified web access portals for patients. This profile CH:ATC defines the audit trail consumption requirements which a community has to meet in order to provide a patients audit trail.

<div markdown="1" class="stu-note">

[Significant Changes, Open and Closed Issues](changelog.html)

</div>

### Implementation Guide Structure
This implementation guide is organized into this main sections:

* Volume 1 – Integration Profiles
   * [Overview](volume-1.html#overview)
   * [Actors, Transactions and Content Modules](volume-1.html#actors-transactions-and-content-modules)
   * [Integration Profile Options](volume-1.html#integration-profile-options)
   * [Actor Groupings](volume-1.html#actor-groupings)
   * [Overview – Use Cases](volume-1.html#overview--use-cases)
   * [Security Considerations](volume-1.html#security-considerations)
* Volume 2 – Transactions
   * [Constraints on Retrieve ATNA Audit Event [ITI-81]](volume-2.html#constraints-on-retrieve-atna-audit-event-iti-81)
* Volume 3 – Content Profiles
   * [Audit Trail Consumption Event Types](volume-3.html#audit-trail-consumption-event-types)
   * [Document Audit Event Content Profile](volume-3.html#document-audit-event-content-profile)
   * [Policy Audit Event Content Profile](volume-3.html#policy-audit-event-content-profile)
   * [Access Audit Trail Content Profile](volume-3.html#access-audit-trail-content-profile)
   * [HPD Group Entry Audit Event Content Profile](volume-3.html#hpd-group-entry-audit-event-content-profile)

### Conformance Expectations
The key words _must_, _must not_, _required_, _shall_, _shall not_, _should_, _should not_, _recommended_, _may_, and _optional_ in this document are to be interpreted as described in [RFC2119](https://www.ietf.org/rfc/rfc2119.txt).

#### Scope of Precisions
The extensions, restrictions and translations specified apply to the following [IHE IT Infrastructure (ITI) integration profiles](https://profiles.ihe.net/ITI/index.html):

* Technical Framework
   * [Volume 1](https://profiles.ihe.net/ITI/TF/Volume1/index.html), Revision 20.0, August 4, 2023 - Final Text
   * [Volume 2](https://profiles.ihe.net/ITI/TF/Volume2/index.html), Revision 20.0, August 4, 2023 - Final Text
   * [Volume 3](https://profiles.ihe.net/ITI/TF/Volume3/index.html), Revision 20.0, August 4, 2023 - Final Text
* Technical Framework Supplements   
   * [Add RESTful ATNA (Query and Feed)](https://www.ihe.net/uploadedFiles/Documents/ITI/IHE_ITI_Suppl_RESTful-ATNA.pdf), Revision 3.4, August 4, 2023 
   * [Internet User Authorization (IUA)](https://profiles.ihe.net/ITI/IUA/index.html), Revision 2.2, June 17, 2022

### Download and Analysis
You can download this implementation guide in [npm format](https://confluence.hl7.org/display/FHIR/NPM+Package+Specification) from [here](package.tgz).

#### IP Statements
{% include ip-statements.xhtml %}

#### Cross Version Analysis
{% include cross-version-analysis.xhtml %}

#### Dependency Table
{% include dependency-table.xhtml %}

#### Globals Table
{% include globals-table.xhtml %}
