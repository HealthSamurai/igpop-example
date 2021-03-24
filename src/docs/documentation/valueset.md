---
title: ValueSets
---

# ValueSets
---
---

## ValueSet
---

A ValueSet resource instance specifies a set of codes drawn from one or more code systems, intended for use in a particular context. Value sets use CodeSystem resources by referring to them via their canonical reference.

## How to create a new ValueSet
---

Create a yaml file with the `vs.` prefix in the `src` folder.
The template looks as follows:

```
system: https://healthsamurai.github.io/igpop-example/CodeSystem/condition-outcome
description: Condition outcome valueset
concepts:
  - code: resolved
    display: Resolved
  - code: recovering
    display: Recovering
  - code: ongoing
    display: Ongoing
```    