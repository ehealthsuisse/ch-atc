# Implementation Guide CH:ATC

The profile CH:ATC defines the audit trail consumption requirements for the EPR in Switzerland which a community has to provide for a patients audit trail.
This project builds an implmenation guide with [IG Publisher](http://wiki.hl7.org/index.php?title=IG_Publisher_Documentation) from HL7. 
See [ehealth-suisse.ch](https://www.e-health-suisse.ch/startseite.html) for more information about the Electronic Patient Record in Switzerland.

## building the implemenation guide
```
java -Xms3550m -Xmx3550m -jar ./igpublisher/org.hl7.fhir.igpublisher.jar  -ig ig.json -auto-ig-build
```
### using templates

ig.json

  "template": "https://github.com/ahdis/test-template",

for devmode

"template": "/Users/oliveregger/Documents/github/test-template",

## validation with the implemenation guide

### validate dev setup with clone from github

```
java -jar ./validator/org.hl7.fhir.validator.jar examples/auditevent/atc-doc-create-rep-pat.xml -version 3.0 -ig ./output
  .. connect to tx server @ http://tx.fhir.org/r4
-tx: Connect to http://tx.fhir.org/r4
    (v3.0.1-null)
+  .. load IG from ./output
  .. validate [examples/auditevent/atc-doc-create-rep-pat.xml]
-tx: Terminology server: Check for supported code systems for http://hl7.org/fhir/object-type
Success...validating examples/auditevent/atc-doc-create-rep-pat.xml:  error:0 warn:3 info:0
  Warning @ AuditEvent.entity[1].type (line 69, col15) : Unknown Code System http://hl7.org/fhir/object-type
  Warning @ AuditEvent.entity[2].identifier.type (line 83, col19) : None of the codes provided are in the value set http://hl7.org/fhir/ValueSet/identifier-type (http://hl7.org/fhir/ValueSet/identifier-type, and a code should come from this value set unless it has no suitable code) (codes = urn:uuid:2e82c1f6-a085-4c72-9da3-8640a32e42ab#IHE XDS Metadata)
  Warning @ AuditEvent.entity[2].type (line 93, col15) : Unknown Code System http://hl7.org/fhir/object-type
```

### validate ci build of implementation guide

```
java -jar ./validator/org.hl7.fhir.validator.jar examples/auditevent/atc-doc-create-rep-pat.xml -version 3.0 -ig http://build.fhir.org/ig/ahdis/ch-atc/
  .. connect to tx server @ http://tx.fhir.org/r4
-tx: Connect to http://tx.fhir.org/r4
    (v3.0.1-null)
+  .. load IG from http://build.fhir.org/ig/ahdis/ch-atc/
Loading http://build.fhir.org/ig/ahdis/ch-atc/package.tgz to the package cache
  Fetching:. done.
  .. validate [examples/auditevent/atc-doc-create-rep-pat.xml]
-tx: Terminology server: Check for supported code systems for http://hl7.org/fhir/object-type
Success...validating examples/auditevent/atc-doc-create-rep-pat.xml:  error:0 warn:3 info:0
  Warning @ AuditEvent.entity[1].type (line 69, col15) : Unknown Code System http://hl7.org/fhir/object-type
  Warning @ AuditEvent.entity[2].identifier.type (line 83, col19) : None of the codes provided are in the value set http://hl7.org/fhir/ValueSet/identifier-type (http://hl7.org/fhir/ValueSet/identifier-type, and a code should come from this value set unless it has no suitable code) (codes = urn:uuid:2e82c1f6-a085-4c72-9da3-8640a32e42ab#IHE XDS Metadata)
  Warning @ AuditEvent.entity[2].type (line 93, col15) : Unknown Code System http://hl7.org/fhir/object-type
```

### validate published implementation guide

todo, ig needs to be published and registered ...

```
java -jar ./validator/org.hl7.fhir.validator.jar examples/auditevent/atc-doc-create-rep-pat.xml -version 3.0 -ig ch.fhir.ig.atc
  .. connect to tx server @ http://tx.fhir.org/r4
-tx: Connect to http://tx.fhir.org/r4
    (v3.0.1-null)
+  .. load IG from ch.fhir.ig.atc
Exception in thread "main" org.hl7.fhir.exceptions.FHIRException: Unable to find the package source for 'ch.fhir.ig.atc' at http://fhir.ch/ig/ch-atc
	at org.hl7.fhir.utilities.cache.PackageCacheManager.resolvePackage(PackageCacheManager.java:477)
	at org.hl7.fhir.r4.validation.ValidationEngine.resolvePackage(ValidationEngine.java:530)
	at org.hl7.fhir.r4.validation.ValidationEngine.fetchByPackage(ValidationEngine.java:519)
	at org.hl7.fhir.r4.validation.ValidationEngine.loadIgSource(ValidationEngine.java:379)
	at org.hl7.fhir.r4.validation.ValidationEngine.loadIg(ValidationEngine.java:608)
	at org.hl7.fhir.r4.validation.Validator.main(Validator.java:276)
```

