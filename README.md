# igpop-example

## Getting started

You can take a look at [Demo](https://healthsamurai.github.io/igpop-example/profiles/Patient/basic.html) page.

To get example project running locally in a dev mode:

* clone the repo
* cd ig-ae
* execute `npm install` in a command line
* run `git submodule init`
* run `git submodule update`
* execute `./igpop.sh dev` in the command line to run a local server on 8899 (may be changed with -p param: `./igpop.sh dev -p 8891`)
* or `./igpop dev` (on Windows)
* navigate to http://localhost:8899 to see the IG site running

_**Note:**_ you can also set your own port value with `-p {PORT_NAME}` parameter.

In order to generate static pages for presented profiles, valuesets and docs use `./igpop build {BASEURL_VALUE}`. These pages will be stored in a *build* directory.

## Development

Put your profiles in *yaml* format, your markdown files with documentation and valuesets with 'vs.' prefix in *yaml* or *csv* format into *src* directory.

Use `./igpop dev` to see results or `./igpop build {BASEURL_VALUE}` to generate static pages.

Read more about profiles [here](https://github.com/HealthSamurai/igpop#profiles)

## Sources

* See full documentation in [home repo](https://github.com/HealthSamurai/igpop.git)
* [Telegram Chat](https://t.me/igpop)
