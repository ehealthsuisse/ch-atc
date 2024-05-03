There are four different categories of Audit Events in the context of the EPR:

<ol type="a">
    <li>
        Document management (e.g. a document has been uploaded to the EPR of a patient or a list of document metadata has been retrieved)
    </li>
    <li>
        Policy management (e.g. a patient has given a healthcare professional access rights to his EPR)
    </li>
    <li>
        Access Patient Audit Record Repository by a patient or representative (a patient viewed the Audit Trail for the Audit Record Repository)
    </li>
    <li>
        Notification of the patient about the entry of healthcare professionals into a group
    </li>
</ol>

Each category is described as a content profile. These content profiles are based on the AuditEvent Resource, [http://hl7.org/fhir/R4/auditevent.html](http://hl7.org/fhir/R4/auditevent.html).

**TODO**: Text Word   
The AuditEvent Resource has mapping rules to the DICOM audit message format, see FHIR Table 6.4.7.2, http://hl7.org/fhir/R4/auditevent-mappings.html which allows to map to ATNA.

**TODO**: Text Vorschlag -> Table 6.4.7.2 wäre Workflow Pattern? Wäre nicht 6.7.7.4 DICOM gemeint wie hier im Vorschlag?   
The AuditEvent Resource has [mapping rules to the DICOM audit message format](http://hl7.org/fhir/R4/auditevent-mappings.html#dicom), which allows to map to ATNA.

### Audit Trail Consumption Event Types
The following Audit Trail Consumption Event Types are defined and shall be supported, see [EprAuditTrailConsumptionEventTypes](http://fhir.ch/ig/ch-term/ValueSet/EprAuditTrailConsumptionEventType) from [Codesystem 2.16.756.5.30.1.127.3.10.7](https://fhir.ch/ig/ch-term/CodeSystem-2.16.756.5.30.1.127.3.10.7.html).

{:class="table table-bordered"}
| Type | Description | Profile Ref | Opt Community |
| --- | --- | --- | --- |
| ATC_DOC_CREATE | Document upload | [Document Audit Event Content Profile](#document-audit-event-content-profile) | R |
| ATC_DOC_READ | Document retrieval | [Document Audit Event Content Profile](#document-audit-event-content-profile) | R |
| ATC_DOC_UPDATE | Document or Document Metadata update | [Document Audit Event Content Profile](#document-audit-event-content-profile) | R |
| ATC_DOC_DELETE | Document removal | [Document Audit Event Content Profile](#document-audit-event-content-profile) | R |
| ATC_DOC_SEARCH | Document search | [Document Audit Event Content Profile](#document-audit-event-content-profile) | R |
| ATC_POL_CREATE_AUT_PART_AL | Authorize participants to access level/date | [Policy Audit Event Content Profile](#policy-audit-event-content-profile) | R, (NP if not reference community) |
| ATC_POL_UPDATE_AUT_PART_AL | Update access level/date of authorized participants | [Policy Audit Event Content Profile](#policy-audit-event-content-profile) | R, (NP: if not reference community) |
| ATC_POL_REMOVE_AUT_PART_AL | Remove authorization for participants | [Policy Audit Event Content Profile](#policy-audit-event-content-profile) | R, (NP: if not reference community) |
| ATC_POL_DEF_CONFLEVEL | Set or update default Confidentiality Level | [Policy Audit Event Content Profile](#policy-audit-event-content-profile) | R, (NP: if not reference community) |
| ATC_POL_DIS_EMER_USE | Disabling Emergency Access | [Policy Audit Event Content Profile](#policy-audit-event-content-profile) | R, (NP: if not reference community) |
| ATC_POL_ENA_EMER_USE | Enabling Emergency Access | [Policy Audit Event Content Profile](#policy-audit-event-content-profile) | R, (NP: if not reference community) |
| ATC_POL_INCL_BLACKLIST | Assign Healthcare Professional to Blacklist | [Policy Audit Event Content Profile](#policy-audit-event-content-profile) | R, (NP: if not reference community) |
| ATC_POL_EXL_BLACKLIST | Exclude Healthcare Professional from Blacklist | [Policy Audit Event Content Profile](#policy-audit-event-content-profile) | R, (NP: if not reference community) |
| ATC_LOG_READ | Accessing Patient Audit Record Repository | [Access Audit Trail Content Profile](#access-audit-trail-content-profile) | R |
| ATC_HPD_GROUP_ENTRY_NOTIFY | Entry of healthcare professionals into a group | [HPD Group Entry Audit Event Content Profile](#hpd-group-entry-audit-event-content-profile) | R, (NP: if not reference community) |

_Table 4: Audit Trail Consumption Event Types_


### Document Audit Event Content Profile

This content profile describes Audit Event related to Document Management. The following Data Elements shall be provided:

{:class="table table-bordered"}
<table>
	<tbody>
		<tr>
			<td>
				<p><strong>Data Element</strong></p>
			</td>
			<td>
				<p><strong>Description</strong></p>
			</td>
			<td>
				<p><strong>Property/Value</strong></p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Event Type</p>
			</td>
			<td colspan="2">
				<p>
                    Document upload<br />
                    Document retrieval<br />
                    Document or Document Metadata update<br />
                    Document removal<br />
				    Document search
                </p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Event Date and Time</p>
			</td>
			<td>
				<p>&nbsp;</p>
			</td>
			<td>
				<p>UTC</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Participants</p>
			</td>
			<td>
				<p>&nbsp;</p>
			</td>
			<td>
				<p>&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td rowspan="6">
				<p>Initiator</p>
			</td>
			<td>
				<p>Patient</p>
			</td>
			<td>
				<p>Name</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Representative of patient</p>
			</td>
			<td>
				<p>Name<br />UAP-ID or EPR-SPID</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Authorized Healthcare Professional</p>
			</td>
			<td>
				<p>Name<br />GLN</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Assistant of a Healthcare Professional</p>
			</td>
			<td>
				<p>Name<br />GLN</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Technical User</p>
			</td>
			<td>
				<p>Name<br />Identifier</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Document Administrator</p>
			</td>
			<td>
				<p>Name<br />UAP-ID</p>
			</td>
		</tr>
		<tr>
			<td rowspan="2">
				<p>Responsible<sup><a href="#_ftn1" name="_ftn1">[1]</a></sup></p>
			</td>
			<td>
				<p>Patient</p>
			</td>
			<td>
				<p>Name</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Healthcare Professional</p>
			</td>
			<td>
				<p>Name<br />GLN</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Groups where Healthcare Professional is member</p>
			</td>
			<td>
				<p>&nbsp;</p>
			</td>
			<td>
				<p>Name of Group<br />OID</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Purpose of Use</p>
			</td>
			<td>
				<p>&nbsp;</p>
			</td>
			<td>
				<p>NORM, EMER, AUTO, DICOM_AUTO</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>Patient</p>
			</td>
			<td>
				<p>Involved patient</p>
			</td>
			<td>
				<p>EPR-SPID</p>
			</td>
		</tr>
		<tr>
			<td rowspan="3">
				<p>Document<sup><a href="#_ftn2" name="_ftn2">[2]</a></sup></p>
			</td>
			<td>
				<p>type of document</p>
			</td>
			<td>
				<p>typeCode<sup><a href="#_ftn3" name="_ftn3">[3]</a></sup> (SNOMED CT code)</p>
			</td>
		</tr>
		<tr>
			<td>
				<p>reference to document</p>
			</td>
			<td>
				<p>
                    <a href="https://profiles.ihe.net/ITI/TF/Volume3/ch-4.2.html#4.2.3.2.26">uniqueId</a><br />
                    <a href="https://profiles.ihe.net/ITI/TF/Volume3/ch-4.2.html#4.2.3.2.18">repositoryUniqueId</a><br />
                    <a href="https://profiles.ihe.net/ITI/TF/Volume3/ch-4.2.html#4.2.3.2.12">homeCommunityId</a>
                </p>
			</td>
		</tr>
		<tr>
			<td>
				<p>title of document</p>
			</td>
			<td>
				<p>
                    <a href="https://profiles.ihe.net/ITI/TF/Volume3/ch-4.2.html#4.2.3.2.24">title</a>
                </p>
			</td>
		</tr>
	</tbody>
</table>
<p><sup><a href="#_ftnref1" name="_ftn1">[1]</a></sup> &nbsp;&nbsp; <small>If different from Initiator (Representative of patient acting on behalf of a patient then patient is responsible).</small></p>
<p><sup><a href="#_ftnref2" name="_ftn2">[2]</a></sup> &nbsp;&nbsp; <small>Required for Document upload, Document retrieval, Document or Document Metadata update and Document removal but not for Document search.</small></p>
<p><sup><a href="#_ftnref3" name="_ftn3">[3]</a></sup> &nbsp;&nbsp; <small>Annex 3 EPRO-FDHA, chapter 2.6 type of document (2.16.756.5.30.1.127.3.10.1.27).</small></p>

_Table 5: Document Audit Event Data Elements_

This profile defines the content of the document audit events which a community has to provide for a patient's audit trail. This profile builds on AuditEvent ([http://hl7.org/fhir/R4/auditevent.html](http://hl7.org/fhir/R4/auditevent.html)).


#### Example of a Document Audit Event: Document upload

### Policy Audit Event Content Profile

#### Examples

### Access Audit Trail Content Profile

#### Example

### HPD Group Entry Audit Event Content Profile

#### Example
