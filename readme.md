# Implementation Guide CH:ATC

The profile CH:ATC defines the audit trail consumption requirements for the EPR in Switzerland which a community has to provide for a patients audit trail.
This project builds an implmenation guide with [IG Publisher](http://wiki.hl7.org/index.php?title=IG_Publisher_Documentation) from HL7. 
See [ehealth-suisse.ch](https://www.e-health-suisse.ch/startseite.html) for more information about the Electronic Patient Record in Switzerland.

Version 1.2.0 from 01.3.2018

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

java -cp org.hl7.fhir.validation.cli-3.7.5-SNAPSHOT.jar org.hl7.fhir.r5.validation.Validator ./examples/bundle/ch-atc-iti-81-response-sample.xml -version 3.0 -ig ch.fhir.ig.atc

validator is built with mvn clean from https://github.com/ahdis/org.hl7.fhir.core/tree/develop where the patch
https://github.com/ahdis/org.hl7.fhir.core/tree/oliveregger_conformsto is included.

### validate dev setup with clone from github

```
java -cp org.hl7.fhir.validation.cli-3.7.5-SNAPSHOT.jar org.hl7.fhir.r5.validation.Validator ./examples/bundle/ch-atc-iti-81-response-sample.xml -version 3.0 -ig ./output/package.tgz
FHIR Validation tool Version 3.7.5-SNAPSHOT - Built 2019-02-28T11:06:59.585+01:00 - Git db30d4973636
Arguments: ./examples/bundle/ch-atc-iti-81-response-sample.xml -version 3.0 -ig ./output/package.tgz
 .. connect to tx server @ http://tx.fhir.org
  .. definitions from hl7.fhir.core#3.0.1
    (v3.0.1)
+  .. load IG from ./output/package.tgz
Loading ./output/package.tgz to the package cache
  Fetching:. done.
  .. validate [./examples/bundle/ch-atc-iti-81-response-sample.xml]
Terminology server: Check for supported code systems for urn:uuid:2e82c1f6-a085-4c72-9da3-8640a32e42ab
Success...validating ./examples/bundle/ch-atc-iti-81-response-sample.xml:  error:0 warn:1 info:0
```

### validate ci build of implementation guide

```
java -cp org.hl7.fhir.validation.cli-3.7.5-SNAPSHOT.jar org.hl7.fhir.r5.validation.Validator ./examples/bundle/ch-atc-iti-81-response-sample.xml -version 3.0 -ig http://build.fhir.org/ig/ahdis/ch-atc/
FHIR Validation tool Version 3.7.5-SNAPSHOT - Built 2019-02-28T11:06:59.585+01:00 - Git db30d4973636
Arguments: ./examples/bundle/ch-atc-iti-81-response-sample.xml -version 3.0 -ig http://build.fhir.org/ig/ahdis/ch-atc/
  .. connect to tx server @ http://tx.fhir.org
  .. definitions from hl7.fhir.core#3.0.1
    (v3.0.1)
+  .. load IG from http://build.fhir.org/ig/ahdis/ch-atc/
Loading http://build.fhir.org/ig/ahdis/ch-atc/package.tgz to the package cache
  Fetching:. done.
  .. validate [./examples/bundle/ch-atc-iti-81-response-sample.xml]
Terminology server: Check for supported code systems for urn:uuid:2e82c1f6-a085-4c72-9da3-8640a32e42ab
Success...validating ./examples/bundle/ch-atc-iti-81-response-sample.xml:  error:0 warn:1 info:0
```

### validate published implementation guide

```
java -cp org.hl7.fhir.validation.cli-3.7.5-SNAPSHOT.jar org.hl7.fhir.r5.validation.Validator ./examples/bule/ch-atc-iti-81-response-sample.xml -version 3.0 -ig ch.fhir.ig.atc
FHIR Validation tool Version 3.7.5-SNAPSHOT - Built 2019-02-28T11:06:59.585+01:00 - Git db30d4973636
Arguments: ./examples/bundle/ch-atc-iti-81-response-sample.xml -version 3.0 -ig ch.fhir.ig.atc
  .. connect to tx server @ http://tx.fhir.org
  .. definitions from hl7.fhir.core#3.0.1
    (v3.0.1)
+  .. load IG from ch.fhir.ig.atc
   ... Using version 1.2.0
  .. validate [./examples/bundle/ch-atc-iti-81-response-sample.xml]
Terminology server: Check for supported code systems for urn:uuid:2e82c1f6-a085-4c72-9da3-8640a32e42ab
Success...validating ./examples/bundle/ch-atc-iti-81-response-sample.xml:  error:0 warn:1 info:0java:608)
	at org.hl7.fhir.r4.validation.Validator.main(Validator.java:276)
```

