# npm
Using the **Node Package Manager**.

## General notes
- npm packages can be installed locally (within a project) or globally.
- To install globally add the ```-g``` flag e.g. ```npm install <MODULE NAME> -g```
- Global installation is required for 'easy' CLI access
- For CLI access of a locally installed package simply add reference with relative path to ```node_module\.bin``` e.g. on Windows: ```node_modules/.bin/<MODULE NAME> --help``` or on Mac: ```./node_modules/.bin/cssmin --help```. see: https://lostechies.com/derickbailey/2012/04/24/executing-a-project-specific-nodenpm-package-a-la-bundle-exec/

## Using npm as an asset pipeline / build tool.
npm can be used instead of an additional task runner e.g. Grunt or Gulp to create asset build workflows.

### Windows command prompt syntax
- **&&** for chaining tasks
- **&** for running tasks simaltaneously
- **<** for inputting the contents (stdin) of a file to a command
- **>** or redirecting output (stdout) of a command and dumping it to a file
- **|** for redirecting output (stdout) of a command and sending it to another command

### Version bumping
run ```npm version patch``` see https://docs.npmjs.com/cli/version for more info on types of levels

### Links
- http://blog.keithcirkel.co.uk/how-to-use-npm-as-a-build-tool/
- http://blog.modulus.io/using-npm-scripts-to-build-asset-pipeline

#### Packages
- JavaScript
  - https://www.npmjs.com/package/uglify-js
  - https://www.npmjs.com/package/jshint
- Sass
  - [See Sass](sass.md)
- CSS
  - https://www.npmjs.com/package/autoprefixer
    - https://www.npmjs.com/package/caniuse-db
    - https://github.com/Fyrd/caniuse
    - https://github.com/ai/browserslist
  - https://www.npmjs.com/package/cssmin

#### Package Notes

###### SassDocs

###### Autoprefixer
Uses the caniuse database and browserslist (for the query)

**To update caniuse database**
```
npm update caniuse-db
```
###### CSS Lint
