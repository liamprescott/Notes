#Sass

A CSS preprocessor extension language that runs either **natively** on Ruby or as a C/C++ port called **LibSass** via .

##Using Sass
Sass is authored using any text based editor.

It is configured and run via:
- The command line
- Third party applications
- A task runner workflow e.g. Grunt, Gulp or npm

####Why use a task runner?
The main benefit of using a task runner is that it makes usage easier, simplifies the configuration process and allows it to be used as part of a wider build workflow.

##Flavours of Sass
There are two options when it comes to running Sass:
1. Using the Ruby based version (runs on ruby)
2. Using libsass, the C version (a C port of the Ruby Sass).

##Installing Ruby Sass
###Step 1.
Open a comand prompt in Administrator mode then type:

  ```
  gem install sass
  ```

#####If you get a permissions error
Need add new security certificates see:
- https://gist.github.com/luislavena/f064211759ee0f806c88
- http://stackoverflow.com/questions/27278966/error-sass-installation-for-windows (May not need to do this if above works)

###Step 2.
To  check the version number type:

  ```
  sass -v
  ```

## LibSass
LibSass is a C/C++ port of Sass. LibSass is just a library. To run requires an implementer e.g:
- [SassC](https://github.com/sass/sassc), a CLI wrapper for several operating systems.
- [Node-sass](https://github.com/sass/node-sass), a library that provides binding for Node.js to libsass.

Initally we'll focus on using Node-sass.

##### Advantages
- Speed, speed, speed! Compile speed is much faster.
- Doesn't require Ruby

##### Disadvantages
- Feature support. But this is becoming less of an issue as the two versions converge. see http://sass-compatibility.github.io/
- Vendor library support. e.g. Compass. There may be some issues.

###Installing Node-sass (and LibSass)
To install with Node-Sass (which installs LibSass requirements):
see: https://github.com/sass/node-sass
  - Navigate to project directory (in command prompt)
  - Type ```npm install node-sass```. This installs the package to the local project only



###Links
- http://sass-lang.com/
- http://sass-lang.com/install
- https://github.com/HugoGiraudel/awesome-sass
- Guidelines
  - http://sass-guidelin.es/
  - http://csswizardry.com/2014/11/when-to-use-extend-when-to-use-a-mixin/
- Architectures / Structuring a Sass project
  - http://www.sitepoint.com/architecture-sass-project/
  - http://thesassway.com/beginner/how-to-structure-a-sass-project
  - http://www.sitepoint.com/look-different-sass-architectures/
- Ruby Sass
  - http://www.liamjaydesigns.com/2012/10/how-to-update-sass-scss/
- Libsass
  - http://libsass.org/
  - https://github.com/sass/libsass
  - https://www.npmjs.com/package/node-sass
  - http://dannyenglander.com/blog/libsass-grunt-do-you-feel-need-for-speed
  - http://benfrain.com/lightning-fast-sass-compiling-with-libsass-node-sass-and-grunt-sass/
  - https://github.com/sindresorhus/grunt-sass [See this for JS options config]
  - http://benfrain.com/lightning-fast-sass-compiling-with-libsass-node-sass-and-grunt-sass/
  - http://www.sitepoint.com/switching-ruby-sass-libsass/
  - http://dannyenglander.com/blog/libsass-grunt-do-you-feel-need-for-speed
  - [Compatibility](http://sass-compatibility.github.io/)
  - Node:
    - https://www.gitbook.com/book/anotheruiguy/nodeexpreslibsass_from-scratch/details
- Visual Studio support
  - http://www.hanselman.com/blog/IntroducingGulpGruntBowerAndNpmSupportForVisualStudio.aspx
