#npm
Node package manager

##General notes
- npm packages can be installed locally (within a project) or globally.
- To install globally add the ```-g``` flag e.g. ```npm install <MODULE NAME> -g```
- Global installation is required for 'easy' CLI access
- For CLI access of a locally installed package simply add reference with relative path to ```node_module\.bin``` e.g. on Windows: ```node_modules\.bin\<MODULE NAME> --help``` or on Mac: ```./node_modules/.bin/cssmin --help```. see: https://lostechies.com/derickbailey/2012/04/24/executing-a-project-specific-nodenpm-package-a-la-bundle-exec/

##Using npm as an asset pipeline / build tool.
Using npm instead of an additional task runner e.g. Grunt or Gulp.


###Links
- http://blog.keithcirkel.co.uk/how-to-use-npm-as-a-build-tool/
- http://blog.modulus.io/using-npm-scripts-to-build-asset-pipeline
-

####Packages
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

####Package Notes

######Autoprefixer
Uses the caniuse database and browserslist (for the query)

**To update caniuse database**
```
npm update caniuse-db
```
