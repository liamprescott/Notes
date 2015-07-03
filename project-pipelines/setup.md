#Setting up a project
Notes about setting up a simple project based on using:

- npm as the pipeline tool
- node-sass for Sass compilation
- autoprefixer to post process Sass generated CSS
- rimraf to clean distribution folders as part of a 'distribute' build
- nodemon to watch for 'production' file updates and automatically run compilation tasks
- livereload to watch for 'distribution' file update and automatically reload any connected browsers
- parallelshell to run compile & livereload at the same time

##1. Create package.json
Do one of the following:

1. Copy an existing one and modify
2. Create from scratch
3. Run ```npm init``` via CLI in the root directory and follow the wizard prompts

*Note: may wish to manually add '''private:"true"'''*


##2. Install core packages
Next we install the core npm packages.
**These are all installed locally via CLI within the project directory**

###Accessing a project specific package when not installed globally (without -g)
For example to check the version number or view the help.
This can be done by running the bin from a relative path e.g. on windows ```.\node_modules\.bin\node-sass --version```

- https://lostechies.com/derickbailey/2012/04/24/executing-a-project-specific-nodenpm-package-a-la-bundle-exec/
- http://superuser.com/questions/547446/start-program-from-relative-path


###node-sass
```npm install node-sass```


###autoprefixer
Autoprefixer setup is a two step process:
1. Install autoprefixer ```npm install autoprefixer```
2. Install postcss-cli which is used to run autoprefixer via the CLI. ````npm install postcss-cli```


- https://github.com/postcss/autoprefixer
- https://github.com/code42day/postcss-cli


###rimraf
rimraf is a deep deletion module for node and will be used to 'clean' folders.
```npm install rimraf```
- https://github.com/isaacs/rimraf


###nodemon
Whilst mainly used to automatically restart node applications during development when files change, it can also be used to automatically run build scripts when files change in 'watched' directories.
- https://github.com/remy/nodemon

```npm install nodemon```

**To stop** when running (in CLI) enter ```CTRL + C```


###live-reload
A live reload server & client.
Runs a live-reload server on the port. It listens to changes on one or more paths and sends reload commands to any browser connected to it.

```npm install live-reload```
- https://github.com/Raynos/live-reload


###todo
- csslint
- cssmin
- concat
- js....everything


####Note
- Adding ```--save``` adds the package to the 'dependencies' object in package.json
- Adding ```--save-dev``` adds the package to the 'devDependencies' object in package.json [more info](http://stackoverflow.com/questions/18875674/whats-the-difference-between-dependencies-devdependencies-and-peerdependencies)


##3. Create npm scripts
Define some simple tasks to run:

These are defined within the 'scripts' object in *package.json*.

```javascript
{
  "name": "",
  "version": "1.0.0",
  "description": "",
  "main": "",
  "author": "",
  "license": "ISC",
  "private": true,
  "config": {},
  "devDependencies": {},
  "scripts": {
    /* Tasks are defined here */
  }
}
```

###Compile main CSS for development
This involves use of 2 scripts (to aid reuse later on).
1. ```"compile:css:main"``` is the core task that compiles 'main.scss' to 'main.css'
2. ```"compile:css:dev"``` simply calls core with some specific config options relevant to dev cycle (as opposed to build / release)

```javascript
"scripts": {
  "compile:css:dev" : "npm run compile:css:main -- --source-map true --output-style expanded",
  "compile:css:main" : "node-sass style/scss/main.scss style/css/main.css"
}

```

###Autoprefix CSS

Ensure that the caniuse database is up to date:
```npm update caniuse-db```

This shows an autoprefixer configured to run via postcss.

```javascript
"scripts": {
  //...Other tasks
  "css:prefix" : "postcss --use autoprefixer -c postcss-options.json -o style/css/main.css style/css/main.css"
}

```

Please note that this config includes configuring the settings via an options.json located in the project root directory.
```javascript
{
  "autoprefixer": {
    "browsers": "> 5%"
  }
}
```



Autoprefixer uses Browserlist to specify target browsers, see:
https://github.com/ai/browserslist#queries


###Create a clean task
Clear out certain folders ready for a clean build.

```javascript
"scripts": {
  //...Other tasks
  "clean:css" : "rimraf style/css/**.*",
}
```


###Sequence tasks
Sequence together the various tasks into a workflow e.g.

```javascript
"scripts": {
  //...Other tasks
  "build:css" : "npm run compile:css:dev && npm run css:prefix"
}

```


###Watching for changes
Watch the file system for changes to files and trigger tasks to run automatically when changes happen.

```javascript
// In this example: watching for changes to .scss files within the style/scss directory
// and running 'npm run build:css' when any file is updated
"scripts": {
  //...Other tasks
  "watch:scss" : "nodemon -e scss -w style/scss -x \"npm run build:css\""
}

```

**Important:**

- To run, the script **must** be enclosed in double quotes("") not single('').
- Therefore these must be **escaped** within the json object (\"...\")  



###Complete scripts object

```javascript
//...
"scripts": {
  //...
}
//...
```

##4. Useful info

###npm
- Adding ```-s``` to an ```npm run $package``` command [silences the output from the package](https://docs.npmjs.com/misc/config#default-configs)




//
