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

#### Entry points

- it's where the user enters into the page
- it's not relevant when the user navigates inside the app
- usually map to one html page

#### On-demand loading

- developers add code split-points to the app
- webpack splits the app into chunks
  - entry points form entry chunks
  - splits points form additional chunks
- syntax for split points
  - require.ensure()
  - AMD require()
  - ES6 System.import

#### Plugins

- Uglify plugin to minify JS beforehand
- gzip plugin to compress assets
- avoid small chunks
- optimize request-size ratio
  - AggressiveMergingPlugin


### Make it better over time

- motivation: user should not be forced to redownload assets they have already downloaded
  - even if an update has been published in the meantime
- users waiting on slow connections get frustrated
- user and server bandwidth limited and expensive

#### Caching

- activate caching for everything
- don't use a per-compilation hash
- use a content hash
- avoid files from changing

#### Caching in Multi-page apps

- preparing a script for each starting page
- user reenters the webapp on different starting pages
- redownloads happen a lot of scripts that are shared
- split prepared script file into common and individual stuff
  - common bundle can be cached between pages
    - CommonsChunkPlugin can be used for this
  - tradeoff is that this is an additional request

#### Advanced caching

- multiple layers for common chunks
  - one for rarely changing things
  - another for often-changing things
  - both can be loaded in parallel
- use different common chunks for different parts of the app
  - more efficient
- commons chunk for on-demand chunks
  - loaded in parallel to the on-demand chunk

### Make it just for you

#### Motivation

- user sessions differ from one another
  - language
  - browser
  - location (different CDN)
- using the same script files for all users is inefficient

#### Targeted builds

- move variables from runtime to compile time
  - language, browser support, CDN url, etc
- prepare script files for every combination

#### Compile-time variables

- defining variables in bundler config
  - configuring language or ES3_SUPPORT

#### Compile-time translations

- I18nPlugin can contain configuration for translation
  - in source, `__('Hello World')` can be used
- map over multiple languages in one webpack config

#### Advanced Config

- parallelization with trivago/parallel-webpack

### Make it beforehand

#### Motivation

- rendering on client can be a additional delay
  - slower devices
  - javascript can be disabled

#### Server-side rendering

- render html on server-side
- serialize state from the server
- should be transparent to the user
- once scripts loaded
  - restore serialized state
  - enhance DOM with script funcionality
- can lead to FOUC
  - styling must be loaded before html
    - styling
    - prerendered html
    - scripts
- challenges
  - rendered html must be equal on client and server
    - best to use same code on client and server
  - node.js can't load css or images
  - initial rendering must not request on-demand code
- webpack can compile bundles for node.js (`target: node`)
  - use different loaders for server-side
  - move styling into head for client-side
- solution for on-demand loading
  - because we can't do on-demand loading for server-side rendering, we must do prefetching of possibly-required chunk

## Frontend management tomorrow?

by [Johannes Ewald](https://twitter.com/jhnnns)

- three deciding web features
  - http/2
  - es2015 modules and System.import()
  - Web Components

### Problems with HTTP1

- limited parallelism (~6)
- head-of-line blocking (browser must wait until server responds)
- protocol overhead (since requests should be stateless, all headers are re-sent every time)
- headers cannot be compressed

### Features in HTTP/2

- multiplexing
- HTTP/2 is a binary protocol
- response prioritization
- header compression
- server push
  - same as inlining (delivering more than one resource at once), but can be cached and prioritized per-file
  - for this we need a dependency tree of dependent resources per entry point
- dependency trees can be generated with:
  - traffic analysis from CDN
  - bundler

### ES2015 modules and System.import()

- `require()` in CommonJS modules is different from ES2015 import
  - import run on compile phase and thus can only be in the top-level scope
  - CommonJS copies required values, ES2015 gives you back a live value instead
    - ES2015 impprts are one-way bindings
- since imports and exports are resolved on compilation, all required modules must be defined beforehand
  - no on-demand loading?
    - System.import() should be the on-demand solution for this
- many questions as to how each runtime should behave with System.import()

### Web Compoents

- do they solve similar problems?
  - yes and no
- Shadow DOM encapsulates DOM nodes into subtrees that are unreachable with CSS selectors
- HTML templates - reusable portion of code
- custom elements
  - API for registering your own html elements with functionality
- HTML imports
  - lots of overlap with ES2015 module loading

### Conclusion

- our toolset has become very complex over the years
- but they ease development and improve performance for users
- rules of thumb
  - don't use tools unless you need them
  - strive for the least abstraction
  - plugin-driven tools will serve you better than monolithic do-everything tools
  - AST-based tools are better than DSLs
- HTTP/2 invalidates some of our current performance best-practices, while others still apply
- ES2015 modules are ready for use with transpilers
- Web components provide useful features, some still up in the air
