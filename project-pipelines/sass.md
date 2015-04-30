#Sass

A CSS preprocessor extension language that runs on Ruby.

##Using Sass
Sass is authored using any text based editor.

It is  configured and run via either:
- The  command line
- Third party applications
- A task runner workflow e.g. Grunt

####Why use Grunt?
The main benefit of using a task runner (Grunt) is that it makes usage easier, simplifies the configuration process and naturally form part of a wider task runner based workflow. See later for more information.

##Installing Sass
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
- Other
  - http://www.liamjaydesigns.com/2012/10/how-to-update-sass-scss/
- Other considerations
  - C Versions of Sass : LibSass / node-sass /
    - http://dannyenglander.com/blog/libsass-grunt-do-you-feel-need-for-speed
    - http://benfrain.com/lightning-fast-sass-compiling-with-libsass-node-sass-and-grunt-sass/



##Compiling Sass with libsass, Node-sass or Grunt-sass instead of Ruby Sass

### libsass
Node-sass is a library that provides binding for Node.js to libsass, the C version of the popular stylesheet preprocessor, Sass.

###Installing
1. Install libsass
1.1 Navigate to project directory
1.2
```
npm install node-sass
```

###Links
- http://libsass.org/
- https://github.com/sass/libsass
- https://www.npmjs.com/package/node-sass
- https://github.com/sindresorhus/grunt-sass [See this for JS options config]
- http://benfrain.com/lightning-fast-sass-compiling-with-libsass-node-sass-and-grunt-sass/
- http://www.sitepoint.com/switching-ruby-sass-libsass/
- http://dannyenglander.com/blog/libsass-grunt-do-you-feel-need-for-speed
- Node:
  - https://www.gitbook.com/book/anotheruiguy/nodeexpreslibsass_from-scratch/details
