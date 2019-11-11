# igpop-example

## Getting started

You can take a look at [Demo](https://healthsamurai.github.io/igpop/profiles/Patient/basic.html) page.

To get example project running locally in a dev mode:
* clone this repo
* use `npm install` to install all required dependencies
* jump to directory with jar file `cd node_modules/igpop/bin/` 
* create npm link via `npm link`
* get back to project's home directory
* use `igpop dev` to start the local server (default port is 8899)

In order to generate statc pages for presented profiles, valuesets and docs use `igpop build`. These pages will be stored in a *build* directory.

## Development

Put your profiles in *yaml* format, your markdown files with documentation and valuesets with 'vs.' prefix in *yaml* or *csv* format into *src* directory.

Use `igpop dev` to see results or `igpop build` to generate static pages.

## Sources

* See full documentation in [home repo](https://github.com/HealthSamurai/igpop.git)
* [Telegram Chat](https://t.me/igpop)
