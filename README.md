# igpop-example

## Getting started

You can take a look at [Demo](https://healthsamurai.github.io/igpop-example/profiles/Patient/basic.html) page.

To get example project running locally in a dev mode:
* clone this repo
* use `npm install` to download latest igpop version
* use `./igpop dev` to start the local server (default port is 8899)

_**Note:**_ you can also set your own port value with `-p {PORT_NAME}` parameter.

In order to generate static pages for presented profiles, valuesets and docs use `./igpop build {BASEURL_VALUE}`. These pages will be stored in a *build* directory.

## Development

Put your profiles in *yaml* format, your markdown files with documentation and valuesets with 'vs.' prefix in *yaml* or *csv* format into *src* directory.

Use `./igpop dev` to see results or `./igpop build {BASEURL_VALUE}` to generate static pages.

Read more about profiles [here](https://github.com/HealthSamurai/igpop#profiles)

## Sources

* See full documentation in [home repo](https://github.com/HealthSamurai/igpop.git)
* [Telegram Chat](https://t.me/igpop)
