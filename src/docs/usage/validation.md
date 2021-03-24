---
title: FHIR Validation
---

# Validate Resources against Profiles
--- 
--- 

## Validate against an IG as a FHIR Package .tgz file's URL

- You can specify an IG .tgz file to validate against in the command:

```java -jar validator_cli.jar -version 4.0.1 path/to/resource -ig https://github.com/HealthSamurai/igpop-example -profile canonical-url```

## Validate a resource with meta element

- You can specify profiles to validate against in the resource's `meta` element:

```
"meta": {
    "profile": ["https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent"]
  }
```  
  
- Then, you can run the following command without specifying the `profile` parameter:  

```java -jar validator_cli.jar -version 4.0.1 path/to/resource -ig https://github.com/HealthSamurai/igpop-example```


## Validation without a terminology server

- Sometimes a terminology server is unavailable. You can set the following parameter to validate without a terminology server.

```-tx n/a``` 

## Validate against a FHIR Package published to FHIR Registry

[Sample FHIR Package](http://registry.fhir.org/package/hl7.fhir.us.patient-reported-outcomes%7C0.2.0)

```java -jar validator_cli.jar -version 4.0.1 resourcesToValidate/adverseEventSample.json -ig hl7.fhir.us.patient-reported-outcomes```

### Validating a single resource in a bundle

To validate a particular resource in the bundle against a given profile: 

-bundle {entry rule} {profile url}

This invokes the nominated profile (by canonical URL) on any entry in any bundle validated that meets the entry rule. The entry rule is either a Resource name, a integer index, or both:

* Patient - validate any patient against the nominated profile 
* 1 - validate the 1th resource (actually the second - index is 0 based) against the nominated profile
* Patient:0 - validate the first patient resource against the nominated profile

#### Example:

```java -jar validator_cli.jar path/to/bundle.json -version 4.0.1 -ig https://github.com/HealthSamurai/igpop-example -bundle Patient:0 https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent```