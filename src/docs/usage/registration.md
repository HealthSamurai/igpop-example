---
title: FHIR IG Package Registration
---

# FHIR IG Package Registration
---
---

If you want to register a new implementation guide, or a new edition of an existing guide, </br> edit `fhir-ig-list.json` and then make your changes into a pull request to the 
[ig-registry repository](https://github.com/FHIR/ig-registry). </br>Then it will be published to the [HL7 FHIR Foundation Enabling health interoperability through FHIR](http://fhir.org/guides/registry/).

Registries:
* [HL7 FHIR Foundation Enabling health interoperability through FHIR](http://fhir.org/guides/registry/)
* [Registry of conformance resources](http://registry.fhir.org/)


## FHIR Packages

The FHIR representation model has its roots in REST, which has its roots in the development of HTTP. </br>
Like REST, the core building block of FHIR is called a resource.  </br>
A FHIR Package is a collection of FHIR Resources (like a directory with a JSON file-per-resource).  </br>
The FHIR community decided to base FHIR package management on the Node Package Manager (NPM) standard.  </br>
The FHIR Package standard is currently a subset of the NPM standard. </br>

Learn more about [FHIR Packages](http://registry.fhir.org/learn)



## Creating & Publishing FHIR Packages

### First, create a package

Create a gzip compressed tarball with files and a package.json file following the [spec](https://confluence.hl7.org/display/FHIR/NPM+Package+Specification).

### Then, publish your package

Create your own package feed and add it to the list of package feeds:
* Create an RSS feed (template at [http://hl7.org/fhir/package-feed.xml](http://hl7.org/fhir/package-feed.xml))
* Register the package feed in [https://github.com/FHIR/ig-registry/blob/master/fhir-ig-list.json](https://github.com/FHIR/ig-registry/blob/master/fhir-ig-list.json) (by making a GitHub PullRequest. </br> The package server will regularly check the RSS feed for new packages.