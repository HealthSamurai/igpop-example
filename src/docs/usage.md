---
title: Usage
---

# Usage
---
---

## Development
---

### Run a Local Server
---

In order to develop the implementation guide, do the following steps:

- Clone the repository [https://github.com/HealthSamurai/igpop-example](https://github.com/HealthSamurai/igpop-example)

```git clone https://github.com/HealthSamurai/igpop-example.git```

- browse to the igpop-example folder

```cd igpop-example```

- Install modules

```npm install```

- Init submodules

```git submodule init```

- Update submodules

```git submodule update```

- Run a local server on the 8891 port (or specify another port if needed)

```./igpop.sh dev -p 8891```

- Navigate to the [http://localhost:8891](http://localhost:8891) to see results of editing

Console output:

```/igpop-example
$ ./igpop.sh dev -p 8891
Dev... (dev -p 8891)
Run server on http://localhost: 8891
```


### Project Structure and Configuration
---

![Project structure](https://github.com/HealthSamurai/igpop-example/blob/master/src/images/project_structure.png?raw=true)


- Update the ig.yaml file in the project root folder:

`id:`  prefix for your FHIR resources<br>
`title:` title displayed on the home page of your IG site<br>
`url:` base URL for your profiles (StructureDefinition.url and fixedUri)<br>
`description:` your IG general description<br>
`fhir:` FHIR version (current value is 4.0.0)<br>


![ig.yaml](https://github.com/HealthSamurai/igpop-example/blob/master/src/images/igyaml.png?raw=true)

- You will need to stop and start server to apply ig.yaml changes


## Edit Profiles and ValueSets
---

When you are running profiles locally, you can edit them directly on the site:

![Editing](https://github.com/HealthSamurai/igpop-example/blob/master/src/images/editing.gif?raw=true)


## Download Structure Definitions
---

- Click the Package link to download a package of FHIR StructureDefinitions and ValueSets
- The package will be downloaded as a zip-archive
- Unzip the archive
- Browse the folder
- The folder will contain FHIR StructureDefinitions and ValueSets

![Package](https://github.com/HealthSamurai/igpop-example/blob/master/src/images/package.gif?raw=true)

## Validate Generated Structure Definitions
--- 

- Having that you downloaded and unzipped the archive with generated structure definitions, you can validate them against the base FHIR specification and your IG.
- Download the official FHIR [validator](https://github.com/hapifhir/org.hl7.fhir.core/releases/latest/download/validator_cli.jar) — a Java jar file that can be used to validate resources ([download page](http://build.fhir.org/downloads.html)). (See the [Validator documentation](https://confluence.hl7.org/display/FHIR/Using+the+FHIR+Validator))
- Say, you've extracted files to the `adverse-event-profile` folder. Then, you will run the following command from the parent folder.
- Run the validator:

```java -jar validator_cli.jar -version 4.0.1 profiles-folder/* -ig ig-folder/ -recurse```

See more [Using the FHIR Validator](https://confluence.hl7.org/display/FHIR/Using+the+FHIR+Validator).


## Validate Resources against AZ Profiles
--- 

### Validate against an IG as a FHIR Package .tgz file's URL

- You can specify an IG .tgz file to validate against in the command:

```java -jar validator_cli.jar -version 4.0.1 path/to/resource -ig https://github.com/HealthSamurai/igpop-example/raw/master/package/package.tgz  -profile profile/StructureDefinition/url```

- Example 1:

```java -jar validator_cli.jar -version 4.0.1 resourcesToValidate/adverseEventSample.json -ig https://github.com/HealthSamurai/igpop-example/raw/master/package/package.tgz -profile https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent```

- Example 2:

```java -jar validator_cli.jar -version 4.0.1 "docs/for review/fixed/New Adverse Event FHIR payload.json" -ig https://github.com/HealthSamurai/igpop-example/raw/master/package/package.tgz -profile https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent```

- Example 3 (fast):

```java -jar validator_cli.jar -version 4.0.1 "docs/for review/fixed/New Adverse Event FHIR payload.json" -tx n/a```

- Example 4:

```java -jar validator_cli.jar -version 4.0.1 "docs/for review/fixed/New Adverse Event FHIR payload.json" -ig https://github.com/HealthSamurai/igpop-example/raw/master/package/package.tgz -tx n/a```


### Validate against an IG as a FHIR Package .tgz local file

- You can specify an IG .tgz local file to validate against in the command:

```java -jar validator_cli.jar -version 4.0.1 path/to/resource.json -ig D:/path/to/package.tgz -profile profile/canonical/url```

- Example:
  
```java -jar validator_cli.jar -version 4.0.1 resourcesToValidate/adverseEventSample.json -ig D:/Work/Healthsamurai/az-fhir-profiles/package.tgz -profile https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent```


### Validate against an IG as a local folder

- You can download an IG files and validate resources against it with the `recurse` parameter:

```java -jar validator_cli.jar -version 4.0.1 path/to/resource -ig path/to/ig/folder/ -recurse -profile profile/canonical/url```

- Example:

```java -jar validator_cli.jar -version 4.0.1 resourcesToValidate/adverseEventSample.json -ig adverse-event-profile/ -recurse -profile https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent```

### Validate a resource with meta element

- You can specify profiles to validate against in the resource's `meta` element:

```
"meta": {
    "profile": ["https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent"]
  }
```  
  
- Then, you can run the following command without specifying the `profile` parameter:  

```java -jar validator_cli.jar -version 4.0.1 path/to/resource -ig https://github.com/HealthSamurai/igpop-example/raw/master/package/package.tgz```

- Example:
  
```java -jar validator_cli.jar -version 4.0.1 resourcesToValidate/adverseEventSample.json -ig https://github.com/HealthSamurai/igpop-example/raw/master/package/package.tgz```

### Validation without a terminology server

- Sometimes a terminology server is unavailable. You can set the following parameter to validate without a terminology server.

```-tx n/a``` 

- Example: 
  
```java -jar validator_cli.jar -version 4.0.1 resourcesToValidate/adverseEventSample.json -ig https://github.com/HealthSamurai/igpop-example/raw/master/package/package.tgz -profile https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent -tx n/a```

### Validate against a FHIR Package published to FHIR Registry

[Sample FHIR Package](http://registry.fhir.org/package/hl7.fhir.us.patient-reported-outcomes%7C0.2.0)

```java -jar validator_cli.jar -version 4.0.1 resourcesToValidate/adverseEventSample.json -ig hl7.fhir.us.patient-reported-outcomes```

### Validate against an IG files by their URLs

```java -jar validator_cli.jar -version 4.0.1 resourcesToValidate/adverseEventSample.json -profile https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent -ig https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent.json -ig https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent-AZEmployeeReporter.json -ig https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent-lateReason.json -ig https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent-localReference.json -ig https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent-positiveDechallenge.json -ig https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent-positiveRechallenge.json -ig https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent-programNumber.json -ig https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent-rechallenge.json -ig https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent-reporterType.json -ig https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent-sourceType.json -ig https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent-surveyStatus.json -ig https://healthsamurai.github.io/igpop-example/ValueSet/survey-status.json -ig https://healthsamurai.github.io/igpop-example/ValueSet/intelligent-source.json```



### Validating a single resource in a bundle

To validate a particular resource in the bundle against a given profile: 

-bundle {entry rule} {profile url}

This invokes the nominated profile (by canonical URL) on any entry in any bundle validated that meets the entry rule. The entry rule is either a Resource name, a integer index, or both:

* Patient - validate any patient against the nominated profile 
* 1 - validate the 1th resource (actually the second - index is 0 based) against the nominated profile
* Patient:0 - validate the first patient resource against the nominated profile

#### Example:

```java -jar validator_cli.jar path/to/bundle.json -version 4.0.1 -ig https://github.com/HealthSamurai/igpop-example/raw/master/package/package.tgz -bundle Patient:0 https://healthsamurai.github.io/igpop-example/StructureDefinition/AdverseEvent```

## Create new profile

See the [IGPOP spec](https://github.com/HealthSamurai/igpop/blob/master/igpop.md).

