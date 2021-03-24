---
title: Development
---

# Development
---
---

## Project Structure
---

<pre>
docs/
  Intro.md - documentation pages
src/ - contains profiles and valueset definitions
  Patient.yaml - profile for patient
  Observation/
     bmi.yaml - specific profile for observation
  vs.gender.yaml - valueset definition
  vs.gender.csv  - codes for valueset
  cs.condition-outcome.yaml - codesystem definition
ig.yaml - manifest file
</pre>

## Project Configuration
---

- Update the ig.yaml file in the project root folder:

`id:`  prefix for your FHIR resources<br>
`title:` title displayed on the home page of your IG site<br>
`url:` base URL for your profiles (StructureDefinition.url and fixedUri)<br>
`description:` your IG general description<br>
`fhir:` FHIR version (current value is 4.0.0)<br>

- You will need to stop and start server to apply ig.yaml changes

## Run a Local Server
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



