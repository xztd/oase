# xztd/oase

## Motivation

* start as a playground to envision ideas around the react ecosystem
* as a lot of ui libs cater for a 90% use case coverage, oase should provide a lower level build block idea
* as a lot of ui libs have an overwhelming interfacem oase should provide a minimal footprint

## Goals

* develop a clean and simple UI components library with a minimal props, foster composition
* make the components easy composable
* provide minimal set of styling and props that are adequate for the scope of the components responsibility
* custom styling should be done via css not via props interpretation
* provide a default Theme and useful css mixins
* develop components by use cases
* get inspired by chakra-ui, Googles material Design, Adobes react-spectrum, Microsoft Fluent Design System
* with minimal dom structure and semantically correct useed html tags
* lower level bsaeline for concrete impl of ui libs
* provide components and utils to increase the DX/DI (Developer Experience / Developer Interface)

### why lerna?
As there are different tools then lerna to manage a monorepo, lerna is widely adopted in the opensource community and is quite mature.

There are tools like npm 7 with workspaces, pnpm and rush, yarn 2 to name a few. But lerna is still the number 1 in adoption.

### why webpack and rollup?
For all libraries rollup will be used as bundler as it is fast and has a minimal overhead. Rollup is optimized for libraries.
Further libraries are primarily targeted for ES Next features

For all application webpack is the bundler of choice, as it is optimized for apps and has a very powerful toolchain for that purpose.

## Technologies / Packages

The project is based on the following core technologies but not limited to and the list will grow over time.

### globally used

* node 14.*
* yarn 1.22.*
* lerna 4.*
* rollup 2.*
* webpack 5.*
* babel 7.*
* typescript 4.*

### tooling

* eslint
* jest
* Docker
* storybook
* commitlint

### ecosystem

* react
* react-router
* formik
* react-spring
