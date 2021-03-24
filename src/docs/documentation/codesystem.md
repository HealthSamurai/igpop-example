---
title: CodeSystems
---

# CodeSystems
---
---

## CodeSystem
---

A CodeSystem resource declares the existence of and describes a code system or code system supplement and its key properties, and optionally defines a part or all of its content. Also known as Ontology, Terminology, or Enumeration.

## How to create a new CodeSystem
---

Create a yaml file with the `cs.` prefix in the `src` folder.
The template looks as follows:

```
description: Defines possible condition outcomes
content: complete
title: Condition Outcome
name: ConditionOutcome
version: 0.1.0
status: active
date: 2021-01-19T13:20:31+00:00
publisher: US Core
concepts:
- code: resolved
  display: Resolved
- code: recovering
  display: Recovering
- code: ongoing
  display: Ongoing
- code: resolvedWithSequelae
  display: Resolved with Sequelae
- code: fatal
  display: Fatal
- code: unknown
  display: Unknown
- code: recovered
  display: Recovered
```