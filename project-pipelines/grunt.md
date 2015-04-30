#Grunt
A Javascript Task Runner used to automate tasks, in the most part via plugins.

####For example a project could be setup such that
- **When changes are made to Sass files:** The CSS files are auto generated, linted and autoprefixed with vendor prefixes before all open browsers are automatically refreshed.
- **When JavaScript files are ready for deployment:** The JS files are automatically, linted, minified, uglified and concatenated and packaged ready to go.

*These are just a couple of v.simple examples.*

##Installing Grunt

Whilst it can be installed globally by installing on a project by project basis it can be declared as an explicit dependancy.

Therefore when `npm install` is run in the project directory, npm knows to grab Grunt as well as the other project dependencies.

A project is described via a `package.json` which contains details such as name, description, version number, authors, licence, dependencies etc.

###Install Grunt CLI
This is Grunt's command line interface. Installed globally so that it doesn't need to be installed for each project.

`npm install -g grunt-cli`

>Note that installing grunt-cli does not install the Grunt task runner! The job of the Grunt CLI is simple: run the version of Grunt which has been installed next to a Gruntfile. This allows multiple versions of Grunt to be installed on the same machine simultaneously.
[http://gruntjs.com/getting-started]

###Install Grunt in a project
1. Create `package.json` in the root folder.

    #####Automatically create via npm
    1. Navigate to project folder in comand prompt:

        `cd c\Projects\Example Project`

    2. Run `npm init`

        This will will ask a few simple questions about the project. Either answer or hit 'enter' (can be updated later).

    #####Manually create file
    1. Simply create a file with the following content:

        ```js
        {
          "name": "project name",
          "version": "0.1.0",
          "devDependencies": {}
        }
        ```

        Other settings can be added see: https://docs.npmjs.com/files/package.json

    **Note:** If not for public consumption need to mark project as private by adding `"private": true`.

2. Install Grunt **in the project** and add to **package.json** by navigating to the project folder and running

    `npm install grunt --save-dev`

##Configuring Grunt

##The Configuration file

##Running Grunt

##Installing Grunt plugins

##Links
- http://gruntjs.com/
- Intro Guides
    - http://martinbean.co.uk/blog/2014/06/08/a-primer-to-using-grunt/
    - http://24ways.org/2013/grunt-is-not-weird-and-hard/
    - http://ryanchristiani.com/getting-started-with-grunt-and-sass/
    - http://www.wearejh.com/development/frontend-automation-with-grunt-sass-browsersync/
- Documentation
    - http://gruntjs.com/getting-started
    - http://gruntjs.com/configuring-tasks
- Plugins
    - Autoprefixer:
        - https://css-tricks.com/autoprefixer/
        - https://github.com/postcss/autoprefixer
        - https://github.com/nDmitry/grunt-autoprefixer
    - BrowserSync
        - http://www.browsersync.io/
    - Concat:
        - https://github.com/gruntjs/grunt-contrib-concat
        - https://www.npmjs.com/package/grunt-contrib-concat
    - Sass:
        - https://github.com/gruntjs/grunt-contrib-sass
    - SassDoc:
    - Watch:
