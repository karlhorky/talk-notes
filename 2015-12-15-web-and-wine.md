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

## [Advanced Frontend Optimization with Webpack](https://sokra.github.io/slides/frontend-optimize)

by [Tobias Koppers](https://github.com/sokra)

- created Webpack a few years ago

### Making things faster

- motivation: users get annoyed by slow apps
- users may quit early while loading
- smaller
  - less bandwidth usage
- simplest and best: make it smaller
- reduce the amounts of requests
- nobody adds lots of script tags
  - now everything is concatenated and combined
- many apps are just using concat for everything
- but there are problems with this:
  - large concatenated file
  - many unnecessary bytes are transferred
- loading everything as separate requests is also not great - many requests

#### Recommendations

- just load what the user needs at the current point in time (for instance, for a profile, load the resources just for this page)
- gzip everything
- try to guess what the user will need (if the user clicks on the search field, we can start loading the search resources)

#### Example interactions

- user opens the web app on the settings page, gets a bundle for this page
- user clicks on the profile page, gets an on-demand bundle for profile
- user enters some text into the search field, the bundle for the search can be prefetched
- but don't prepare too many small on-demand files
- always load files in parallel when split up
- loading indicators for on-demand contents
- handle failures in on-demand loading

#### Reducing the number of requests

- js + js: concat
- img + img: sprites
- css + css: concat
- js + html: inlineHTML
- etc.

#### Inlining

- don't always inline
  - it's not progressive
  - inlining can increase the size (base64)
  - resource may not be used
  - flash of unstyled content may appear if css moved from head to body
  - not parallizable or cachable

### Frontend management tomorrow?
