### Introduction

TBD bisheriger text:   
This profile defines the audit trail consumption requirements a community has to provide for a patient. The profile CH ATC defines and precises the actors and transaction [ITI-81] of the [IHE IT Infrastructure Technical Framework Supplement Add RESTful Query to ATNA](http://www.ihe.net/uploadedFiles/Documents/ITI/IHE_ITI_Suppl_RESTful-ATNA.pdf) and defines the content of the Audit Messages. The different types of the Audit Messages are based on the requirements for Document and Policy Access management in order to achieve the Swiss regulation needs on the audit trail access by patients. These Audit Event types differ from the Audit Events which have also to be logged according to the IHE / CH:ATNA requirements.

The CH ATC profile text in the National Integration Profiles (SR816.11, Annex 5, Extension 2) is normative, this implementation guide is informative. This implementation guide is built with [IG Publisher](https://confluence.hl7.org/display/FHIR/IG+Publisher+Documentation) from HL7. See [e-health-suisse.ch](https://www.e-health-suisse.ch/startseite.html) for more information about the Electronic Patient Record in Switzerland.

TBD text aus word:    
This document fulfils the Swiss regulations of the Ordinance on the Electronic Patient Record (EPRO, SR 816.11). The EPRO and the EPRO-FDHA (SR 816.111) are published in Official Compilation of Federal Legislation (available in [German](https://www.admin.ch/opc/de/classified-compilation/20111795/index.html), [French](https://www.admin.ch/opc/fr/classified-compilation/20111795/index.html) and [Italian](https://www.admin.ch/opc/it/classified-compilation/20111795/index.html)).
The Swiss Electronic Health Record (EPR) depends on an IHE XDS and multi-community based system where the patient not only consents to the creation and use of the record, but does so by explicitly defining access rules through a patient portal.
Patients – and, if existing, their representatives – have the right to access the audit trail within the EPR circle of trust. The access to the audit trail will be provided by certified web access portals for patients. This profile CH:ATC defines the audit trail consumption requirements which a community has to meet in order to provide a patients audit trail.


<div markdown="1" class="stu-note">

[Significant Changes, Open and Closed Issues](changelog.html)

</div>

### Implementation Guide Structure
This IG is organized into the following sections:

* Volume 1 – Integration Profiles
   * [Overview]()
   * [Actors, Transactions and Content Modules]()
   * [Integration Profile Options]()
   * [Actor Groupings]()
   * [Overview – Use Cases]()
   * [Security Considerations]()
* Volume 2 – Transactions
   * [Constraints on Retrieve ATNA Audit Event [ITI-81]]()
* Volume 3 – Content Profiles
   * [Audit Trail Consumption Event Types]()
   * [Document Audit Event Content Profile]()
   * [Policy Audit Event Content Profile]()
   * [Access Audit Trail Content Profile]()
   * [HPD Group Entry Audit Event Content Profile]()


### Download and Analysis

You can **download** this implementation guide in [npm format](https://confluence.hl7.org/display/FHIR/NPM+Package+Specification) from [here](package.tgz).

#### IP Statements

{% include ip-statements.xhtml %}

#### Cross Version Analysis

{% include cross-version-analysis.xhtml %}

#### Dependency Table

{% include dependency-table.xhtml %}

#### Globals Table

{% include globals-table.xhtml %}
