# Polymer Summit

## Opening keynote

by [Matthew McNulty](https://twitter.com/mattsmcnulty) & [Taylor Savage](https://twitter.com/taylorthesavage)

### Decreasing developer friction

- Problem: "There's an element for that*" * if you download bower and install the element and its dependencies
- Solution: polygit - an easy way to get started without the overhead

- Problem: white blank page problem
- Solution: polylint - shows you errors as you code

- Problem: It's tough to measure the cost of elements
- Solution: polydev - to measure the cost of one particular element

- http/2 - performance improvements

### The LEGO model of the web

- polymer's LEGO connectors are the web's tags, attributes and properties

## [Thinking in Polymer](https://github.com/kevinpschaaf/chat-view-paper)

by [Kevin Schaaf](https://twitter.com/kevinpschaaf)

### Mindset of building with Polymer

#### DOM is the framework
- using the frameworky parts of the web standards that already exist
- using the component model of the DOM
- data flow through attributes, properties and events
- declarative syntax in HTML
- this stuff all existed for a long time, but the missing ingredient was custom elements
  - now authors can create their own elements using this powerful browser platform
- by making the pieces larger and easier to understand, we reduce the amount of concepts that web developers need to know
- interoperable and reusable
- no lock-in

### Mission of polymer
- Polymer wants to make building custom elements as easy as possible
- reducing the boilerplate required
- making writing custom elements fun

### How far can polymer alone get you?
- can custom elements alone build an application?


### Thinking locally
- to avoid getting overwhelmed, you're not going to hold all the complexity of app in your head
- break functionality down into small parts
- "what could I use to solve this one problem?"
- using the mediator pattern
  - Objects no longer communicate directly, but through a mediator
  - a custom element made up of multiple children with their own API talking to each other through a business logic layer
  - these custom elements have their own API to be used externally, to be nested in other parent elements

#### Example app
- focusing first on the element to set the label (&lt;input-header&gt;)
- in the mediator pattern, the label property is observed and then set in the fields
- mediator pattern is much easier with data-binding
- this &lt;input-header&gt; element can now be integrated into a parent for the message thread
- the thread element can also include a dom-repeat element for all the messages


## [End to end with Polymer](https://polymer-todo.firebaseapp.com)

by [Rob Dodson](https://twitter.com/rob_dodson)

- Problem: starting is difficult (staring at a blank page). Web development is complicated with all the different tooling and libraries. Researching takes a lot fo time, and you don't make any progress.
- Solution: polymer starter kit
  - responsive app layout
  - routing
  - components for almost any app
  - unit test support with Web Component Tester
  - complete build chain to bringing it to production

- Problem: breaking up an app into smaller components
- Solution: analysis of the needs of an application

### Example App - Todo list
- data element: may seem strange to put this in the html, but an easy pattern to sync data declaratively

- Problem: persisting data
- Solution: use a JavaScript API of a Database as a Service such as Firebase

- Firebase supports intermittent or offline connections too with a local cache of the data to be written when the user comes online again

- Problem: productionizing your app
- Solution: use gulp build chain and a PAAS like Firebase Hosting

## [Using ES2015 (ES6) with Polymer](https://github.com/ebidel/polymer-experiments)

by [Eric Bidelman](https://twitter.com/ebidel)

- ES2015: new features coming to browsers
- you can actually use a lot of the features in the newest browsers today
- template tags and custom elements and other specs of web elements are the base of the web platform
- polymer is built on top of this
- Polymer wants to evolve with the web platform
- Pull request for ES6 open in the polymer repo
  - classes

### Intro to small ES6 features

- Spread operator: accept arrays as parameters, expand
- default parameters in function definitions
- arrow functions
  - shorter function definitions with arrows
  - this is lexically scoped
- Object literal shorthand - shorter definitions of methods
- template strings
  - finally multiline strings
  - variable substitution (interpolation)
  - tagged template strings - apply functions to a string (can be used for metaprogramming)
- real class syntax with keyword
  - can be used to define custom elements extended from other html elements, either with vanilla custom elements or through Polymer

## Testing Polymer Web Components

by [Chris Joel](https://twitter.com/robodynamo)

- assumption: web components are difficult to test
- reality: it's actually not too hard

### Principles of testing
- repeatability
- DRY

### Web Component Tester
- mocha, chai, sinon
- selenium built in (multiple browsers)
- Sauce labs is built in
- extensible
- easy as creating an html document for the test
  - including WCT at the top, and then the element
  - adding the element
  - writing a test for the element
  - can be run in the browser
  - WCT automates multiple browsers

### Leaky state in HTML
- state leak is a common accident in test suites
  - setting properties that affect other tests (global elements)
  - order dependency
- there's an element for that - &lt;test-fixture&gt;
  - automatically tears down html by removing from the DOM

### More tools
- stub - mocha helper
  - substitutes methods on elements to capture side effects
  - uses sinon spies under the hood
- replace - mocha helper
  - replace elements with other elements to avoid side effects

### Accessibility
- Accessibility Developer Tools - chrome extension
- for doing an audit on your site
- these development tools are integrated in the WCT now (a11ySuite())

## Platinum Elements (Service Worker)

by [Mat Scales](https://twitter.com/wibblymat)

- Platinum Elements: making using the greatest and latest web platform features easy
  - Offline, push and more
- Lots of cool new features, but tons to learn and lots of code
- most of the features are implemented in just a few newest browser (or just Chrome)
  - graceful degradation for other browsers

### Offline
- removing dependency on the network
- saving all app resources on the device
- offline support is not just useful for people without any connectivity - also for he larger set of people with bad connectivity
  - also for people with good connections - don't need to go to the network at all in some cases
- games, for instance, can be completely offline
- there's an element for that
  - &lt;platinum-sw&gt;
  - service worker acts as an intermediary between the app and the server, writing to and reading from a cache
- cache strategies
  - networkOnly - only from network
  - networkFirst - try network first
  - cacheFirst - use cache first if available - can be used for read-through caching
  - fastest - use the fastest out of network and cache
  - you can define your own cache strategy

### Messaging (push notifications)
- you get a message when something happened on a remote server
- there's an element for that - &lt;platinum-push-messaging&gt;
- can be set up with Google Cloud Messaging

### Device access (experimental - only on ChromeOS)
- access to external bluetooth devices such as heart sensors, etc.
- Web Bluetooth API
- there's an element for that - &lt;platinum-bluetooth-device&gt;
- not all devices are passive - this can be used to actively control devices as well

## There's an element for that - but what if there isn't?

by [Surma](https://twitter.com/surmair)

- design patterns to integrate well with the ecosystem
- if you want to wrap an API such as your own
  - hide the complexity, but keep configurability

### Demo: reddit element wrapping the read-only Reddit API
- using jsonp
- keeping the API URL declarative in the html

### Hiding complexity
- try to break components into sub-elements as much as possible


## Adaptive UI with Material Design and Paper Elements

by [Zach Gibson](***), [Yuin Chen](***), [Addy Osmani](https://twitter.com/addyosmani)

- the trick is to understand patterns we can use and the different capabilities of the user's browser and device to design across multiple devices
- material design - single, unified pattern
- material design is Google's reference design pattern for the web
- 100k material projects
- adaptive design: provides the appropriate content, in the right form, based on context, content, input method, user needs and device limitations
- material design team and polymer team are starting with:
  - nomenclature
  - grids
  - breakpoints
  - design guidelines
  - smart paper elements

### Defining Nomenclature
- what it is
- temporal (persistent, temporary)
- its location
- what it contains
- its behavior

### Grid
- defining a 12-column grid that works in most situations

### Breakpoints
- creating consistency in layouts across many device screen sizes

### Polymer and material breakpoints
- all breakpoints are included in Polymer starter kit
- &lt;iron-media-query&gt; - data-binding and callbacks for media queries

### Position
- optimizing position and sizing of elements for the screen size

### Transforms
- ex. left nav pattern is normal on mobile phones, but a nav bar may be better on desktop

### Reflowing
- moving components or columns around

### Reveal
- revealing more options or content on different screens

### Dividing
- dividing screens based on size

### Expanding
- surfaces expanding on different screen sizes

### Resources
- device library
- resizer
- material design spec

## Polymer's Styling System (how to style elements without dragons)

by [Monica Dinculescu](https://twitter.com/notwaldorf)

- open source is great for CSS
- but everything is global in CSS unfortunately
  - traditionally, you just have to name things uniquely, which doesn't scale
- the shadow DOM helps: scoping for CSS
- but problems with the shadow DOM - you cannot style inside the shadow DOM
  - except for /deep/ and ::shadow
  - but these are hacky and break the promise of encapsulation
- but there's a better option - define a styling API through CSS custom properties and mixins for the custom elements
  - this enables themes

## Polymer's Animation System

by [Yvonne Yip](***)

- animations help users understand how an application works by creating connections between views
- Polymer philosophy: everything is an element
  - even animations

### Animation elements
- reusability
- pluggability (combining animations)
- flexibility (configurability)
- easy to use

### Web animations ([w3c spec](https://w3c.github.io/web-animations))
- nested and sequenced animations
- powerful animations at runtime without css
- playback controls
- jank free
- keyframeEffects allow you to animate keyframes
  - groupEffects allow animations of multiple elements at the same time

### Neon Elements from Polymer
- divide elements into animatable and animations
- makes keyframeEffects easier
- you can add event listeners for the animations
- sharedElements property can be used to define elements that persist across views

## Lightning Talk: Upgrading to 1.0 with polyup

by [Peter Burns](https://twitter.com/rictic)

- 0.5 to 1.0
  - massive performance improvements
  - Shadow DOM polyfill and Data binding system were rewritten

### polyup
- node.js binary to transform your code to 1.0
- how is this possible? because Polymer is declarative
  - declarative code is simple, and can be parsed and upgraded much easier than imperative code

## Lightning Talk: Polymer's Gesture System

by [Dan Freedman](https://twitter.com/danfreedman)

- why are gestures important? they allow the user to quickly interact with applications based on devices capabilities
- polymer team made a gesture system

### down and up
- abstracted listeners for mousedown, mouseup, touchstart and touchend

### tap
- abstracted listener for click

### track
- drag and drop that actually works
- can be locked to an axis

## A11y with Polymer

by [Alice Boxhall](***), [Laura Palmaro](***)

- what are accessible technologies: services and products for people with disabilities
- 1 in 6 in the world has a disability
- what's important is customizability of the UI (zooming)
- some users that need accessible technologies:
  - users that need screen capturing
  - users that need sign language output
  - users with difficulty or inability using hardware like physical mice
  - users with dyslexia - needs help with keeping focus
  - aging population

### Polymer
- polymer team created best-practices checklist for elements
- the team maintains an a11y testing snapshot
- custom elements can have attributes like tabIndex defined using hostAttributes
- &lt;iron-a11y-keys-behavior&gt; - abstracted API for key events
- iron has mixin behaviors
- paper elements are finished elements built for accessibility

### Accessibility developer tools
- contrast ratio tester


- "disability is the interaction between individuals with a health condition, and personal and environmental factors" - World Health Organization

