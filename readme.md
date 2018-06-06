# Implementation Guide CH:ATC

The profile CH:ATC defines the audit trail consumption requirements for the EPR in Switzerland which a community has to provide for a patients audit trail.
This project builds an implmenation guide with [IG Publisher](http://wiki.hl7.org/index.php?title=IG_Publisher_Documentation) from HL7. 
See [ehealth-suisse.ch](https://www.e-health-suisse.ch/startseite.html) for more information about the Electronic Patient Record in Switzerland.

```
java -Xms3550m -Xmx3550m -jar ./igpublisher/org.hl7.fhir.igpublisher.jar  -ig ig.json -auto-ig-build
```


ig.json

  "template": "https://github.com/FHIR/test-template",

for devmode

"template": "/Users/oliveregger/Documents/github/test-template",