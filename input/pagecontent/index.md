### Introduction

Patients and their representatives have access to the audit trail of the [Electronic Patient Record (EPR)](https://www.fedlex.admin.ch/eli/cc/2017/203/en) via the portal of their reference community. The Swiss profile Audit Trail Consumption (CH ATC) defines the Audit Messages for document management, access policy management, audit trail retrieval by the patient or their representative(s), and logging of group entries of healthcare professionals. This profile uses the IHE transaction [Retrieve ATNA Audit Event [ITI-81]](https://profiles.ihe.net/ITI/TF/Volume2/ITI-81.html) to consume the Audit Messages from all communities. CH ATC is intended for patients to see what has happened in their EPR. It does not replace the logging of the ATNA Audit Events. This profile fulfills the Swiss regulations and is referenced in Annex 5 of the EPRO-FDHA.   
This implementation guide is built with [IG Publisher](https://confluence.hl7.org/display/FHIR/IG+Publisher+Documentation) from HL7. For more information about the EPR, see [patientrecord.ch](https://www.patientrecord.ch/), [e-health-suisse.ch](https://www.e-health-suisse.ch/startseite.html) and [Federal Office of Public Health](https://www.bag.admin.ch/epra).

<div markdown="1" class="stu-note">

This implementation guide is under STU ballot by [HL7 Switzerland](https://www.hl7.ch/) until September 30th, 2024 midnight.   
Please add your feedback via the ‘Propose a change’-link in the footer on the page where you have comments. 

[Significant changes, open and closed issues.](changelog.html)

</div>

### Implementation Guide Structure
This implementation guide is organized into this main sections:

* Volume 1 - Integration Profiles
   * [Overview](volume-1.html#overview)
   * [Actors, Transactions and Content Modules](volume-1.html#actors-transactions-and-content-modules)
   * [Integration Profile Options](volume-1.html#integration-profile-options)
   * [Actor Groupings](volume-1.html#actor-groupings)
   * [Overview - Use Cases](volume-1.html#overview---use-cases)
   * [Security Considerations](volume-1.html#security-considerations)
* Volume 2 - Transactions
   * [Constraints on Retrieve ATNA Audit Event [ITI-81]](volume-2.html#constraints-on-retrieve-atna-audit-event-iti-81)
* Volume 3 - Content Profiles
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
