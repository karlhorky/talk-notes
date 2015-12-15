# Web & Wine

2015-12-15 in Augsburg, Germany

## Frontend management - yesterday, today and tomorrow?

by [Johannes Ewald](https://twitter.com/jhnnns) and [Richard Stromer](https://twitter.com/noxannet)

### How we used to manage our frontend: 3 examples

- roomieplanet.com
  - student project
  - server side rendering with php and smarty
  - almost the same amount of code already on frontend
  - 273 js files including deps
  - no dependency manager (everything in vendor dir)
  - no real module system (everything global)
  - minified with jsmin.php
  - one main.css for all pages
  - no preprocessor or minifier
  - everything uploaded with ftp
  - no asset handling
- moonID
  - online gaming platform
  - statically rendered site
  - classic Django website (server-side rendering)
  - static files managed by Django
  - 23 js files (snippets)
  - building sass files via makefile
  - combination of CSS vendor files and sass
  - JS files included directly via templates
  - combination of jQuery plugins, vendor files and global and site-dependant snippets
- mybraintraining.com
  - Django with Django compressor
    - concatenate
    - minify
    - preprocessors
  - sass and coffeescript in integrated build process
  - Template as entry points with TemplateTags
  - no handling for vendor files
  - partially optimized
  - more Javascript
  - Unified Javascript

### Frontend management today

#### Task Runners

- ex. grunt, gulp
- makefiles in JS
- predefined order
- custom tasks from npm
- tasks applied to set of files
- don't understand contents of files

#### CSS Processors

- ex. Sass, Less, PostCSS
- productivity bosts
- variables
- mixins, functions

#### Template Engines

- ex. Jade, Handlebars
- DRY
- classic templating
- often shipped with MV*

#### Transpilers

- ex. Babel, CoffeeScript
- other languages to JavaScript for specific runtimes like browsers

#### Bundlers

- ex. Browserify, Webpack
- convert multiple types of input files to other types of output files
  - also html, images, css, font
- create a dependency tree by understanding the AST

#### Why do we use all these tools?

- ease of development
- performance in production

### Optimizing page load time

#### Why optimize?

- loading takes too long for users
  - user may leave
  - user may not buy
  - not just about the initial load time, all following requests need to be fast as well

#### Loading doesn't mean that everything is finished

- rendering can start before everything is loaded
- try to optimize for "above the fold" content (visible content in viewport)
- some resources are blocking (block the page from loading further)
  - try to minimize these

#### Google PageSpeed can be used

- tools, best practices, standards, resources
- PageSpeed Insights tool that analyses:
  - compression
  - caching
  - minification
  - response time
  - prioritization of visible content
  - async js and css (non-blocking)
- PageSpeed Modules for servers

### Advanced frontend optimization

### Frontend management tomorrow?
