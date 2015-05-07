#Sass

A CSS preprocessor extension language that runs on Ruby.

##Using Sass
Sass is authored using any text based editor.

It is  configured and run via either:
- The  command line
- Third party applications
- A task runner workflow e.g. Grunt, Gulp or npm (native)

####Why use a task runner?
The main benefit of using a task runner is that it makes usage easier, simplifies the configuration process and naturally form part of a wider task runner based workflow.

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


## libsass
libsass is the C version of Sass. There are a number of ways of using libsass. The one focused on here is Node-sass, a library that provides binding for Node.js to libsass.


###Installing a libsass and Node-sass / Grunt-sass setup
1. To install with Node-Sass (which installs libsass requirements):
see: https://github.com/sass/node-sass
  - Navigate to project directory (in command prompt)
  - Type ```npm install node-sass```. This installs the package to the local project only
2. To install with grunt-sass see: https://github.com/sindresorhus/grunt-sass


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
  - Node:
    - https://www.gitbook.com/book/anotheruiguy/nodeexpreslibsass_from-scratch/details
