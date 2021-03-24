## IGPOP Example FHIR Profiles
---
---

FHIR Package is available by the address: [https://healthsamurai.github.io/igpop-example/package.tgz](https://healthsamurai.github.io/igpop-example/package.tgz)

Example how to validate a FHIR resource against the Igpop Example FHIR IG:

```java -jar validator_cli.jar -version 4.0.1 resourcesToValidate/ -ig https://healthsamurai.github.io/igpop-example```

GitHub Repository: [https://healthsamurai.github.io/igpop-example/](https://healthsamurai.github.io/igpop-example/)

### Welcome to the IGPOP Example FHIR Implementation Guide!
---

#### Site Navigation

On the top navigation bar, there are the following items:

* ##### Docs

Documentation and instructions

* ##### Profiles

Here you can view rendered IGPOP profiles in a brief convenient format

* ##### ValueSets

Here you can view the value sets that are used in the IGPOP profiles

* ##### CodeSystems

Here you can view the code systems defined in the IG

* ##### StructureDefinitions

Here you can view the structure definitions generated from IGPOP profiles

* ##### Package

The Package link downloads a FHIR Package with all FHIR IG resources. <br>
The package will be downloaded as a tgz-archive with a tar-file. <br>Unzip the archive. It'll contain the `package` folder with .index.json, package.json files and CodeSystems, StructureDefinitions, and ValueSets.

