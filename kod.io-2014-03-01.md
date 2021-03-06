[The Chroma Zone - Engineering Color on the Web](http://leaverou.github.io/chroma-zone)
==============================================

by [Lea Verou](https://twitter.com/LeaVerou)

* open source projects
  * prismjs.com
  * -prefix-free
  * css3test.com
* member of css working group, prev. member of w3c

how color works on the screen
-----------------------------

* white pixels made up of 3 subpixels (rgb)
  * can have different order
  * different subpixel intensities for different colors

rgb
---

* can be thought of as a coordinate system
  * can be mapped to a cube
  * most color pickers flatten one of the dimensions and then allow you to tweak the other two
* in css, we can set colors with the rgba() notation or #xxxxxx / #xxx hex notation
  * both forms are confusing
* another option: css color names
  * very ugly colors
  * some newer: super long, racist, or completely crazy (dark gray )
* currentColor in css3
* fun rgb / hsl guessing game: [http://leaverou.github.io/whathecolor/](http://leaverou.github.io/whathecolor/)

hsl
---

* different coord system: can be mapped to a cone
* lightness in hsl is not perceptual lightness for us as humans, because it's just a transformation of rgb
  * lightness is not the same as luminance

enter: relative luminance
-------------------------

* from wcag 2.0, css4
* to achieve perceptual lightness, blue is multiplied by smaller number as green as red

alpha blending
--------------

* compositing two colors and alpha strengths to calculate what the opaque color should be

css4
----

* gray(xx%) - unsupported now, but can be polyfilled with sass
* adjustors: tint, shade, blend


[AngularJS and i18n](http://pascalprecht.github.io/slides/angularjs-and-i18n/#/)
===================

by [Pascal Precht](https://twitter.com/PascalPrecht)

* professional animated gif executer

angularjs
---------

* design as if html had been designed for apps (html++ so to say)
* two way data binding
  * one single source of truth (within scopes)
  * declarative views, don't need to write traditional javascript code
* directives to define functionality on elements
* web components to define your own elements
* routes
* built with testability in mind

internationalization / localization
-----------------------------------

* abstracting your strings for use in different languages, countries
* angular support
  * datetime, number, currency, ngPluralize
  * $locale service (from ngLocale)
  * unfortunately, that's it - can't translate all strings

introducing angular-translate
-----------------------------

* typical components: services, filters, directives
* var replacement
* multi-language
* fallback languages
* missing tranlsation support
* async
* localStorage to save locale
* changing the language at runtime with simple controller method

How to Get More Women in Tech in 5 Steps
========================================

by [Anika Lindtner](https://twitter.com/langziehohr)

* Travis CI supporter of Railsgirls from the start
* very low population of women in
* traditional answers
  * "they're just not so good at it"
  * "they're just not interested"
  * we know that these are not true
* stereotypes are much different today than earlier
* there are no gender-specific abilities
* missing role models
* fear of change

Where can we start?
-------------------

* daily life - talking, why you love what you do
* support and inspire others
* family - raise children to follow their dreams, regardless of gender
* workshops - get people together to get excited about code

Railsgirls summer of code 2013
------------------------------

* workshop
* 3-months, full-time, paid
* raised $80k, were able to support 19 student
* more joined after as well, total 33 students

Which 5 steps?
--------------

* there are no five steps, takes hundreds of small actions to change the culture

[Fly, You Tools!](http://talks.chastell.net)
============================================

by [Piotr Szotkowski](https://twitter.com/chastell)

* typical bug hunting: just like lord of the rings
* piotr working at the warsaw university of tech
* you know there are some nifty things
* you read a lot of blog posts
* you can never remember the tricks

git
---

* git is like a sharp knife, with the handle also a knife, and then fractals into more knives
* ```git rebase --interactive --autosquash``` - holy shit, don't need to do anymore work
* ```--allow-empty``` for first git init commit
* ```git log --oneline --decorate``` for one-line log
* ```git diff --ignore-all-space``` or ```git diff -w``` diffs without whitespace - can be activated as ?w=1 to end of github diff urls

postgres
--------

* wow, all the datatypes! if it were only named better
* curved and square brackets for inclusive and exclusive ranges
* hstore
* JSON

cli
---

### piping ###
* grepping / sorting / uniqing git commit messages for commit statistics
* cutting / xarging / tring / bc to get total migration time
* pipe viewer - show you the progress of something the command line

### interesting commands ###
* ```pgrep``` and ```pkill``` find and kill processes by name instead of id
* ```watch``` - rerun every x seconds
* ```timeout``` kill a process after x time
* ```proxylocal``` expose local port to public

### in bash.profile ###
* ```alias computer,='sudo'``` - ```computer, apt-get install postgresql```


Make Your and Other People’s Life Easier: Do Support!
=====================================================

by [Mike Adolphs](https://twitter.com/fooforge)

* github is
  * code hosting
  * enterprise
  * git training worldwide
  * youtube channel
  * conferences
  * vision: "easier to work together as to work alone"

History of support
------------------
* first version of support: your handbag broke, fix it!
* 1876: telephone
* advent of telephone: remote support
* 20th century: call centers, cramming people into cubicles
* since call centers, support has a bad rep for entry-level employees
* but support is more like firefighting, enabling user to get back to work

Support at github
-----------------

* people in 26 timezones all over the world providing support
* tech support for native clients
* account support
* enterprise team -> just enterprise only
* github trying to merge the two support teams into single team
* support never stops, but support team deserves to take part in company cultural activities too

### Rules ###
* never get into a fight with the customer
* don't insult the customer
* don't endlessly apologize as an excuse
* don't pretend to have superpowers - no single human can know everything
* don't advertise to users without them asking
* don't let yourself get dragged down

### Superfans ###
* when you do following, you gain superfans:
  * support done right and quickly
  * repo corruption quickly cleaned up

Why help out?
-------------

* stable software
* just one dish in the sink at a time - focus on one thing at a time
* who are you really working for? the whole userbase, not upper management
* learning
* empathy - learn how to put yourself in the user's shoes
  * turned Mike into a socializing human being from an angry sysadmin

Vagrant, Packer, Serf: Maximum Potency DevOps
=============================================

by [Mitchell Hashimoto](https://twitter.com/mitchellh)

* devops used to be easier: just start with chef or puppet
* now a lot more confusing: much more saturated terain
* HashiCorp
  * try to build tools to solve pain points for companies
  * tools: Vagrant, Packer, SERF

application lifecycle
---------------------
=== 1) development ===
* your work should be able to be easily accessible anywhere
* make changes, see changes (golden circle of code, save, reload)
* "it works on my machine"
* collaboration
=== 2) deployment ===
* deployment
  * complex, multiple steps
  * no companies happy with the
=== 3) maintenance ===
* monitoring
* updating
* orchestrating (managing load balancing, scaling)


* pragmatic goal of devops: making the lifecycle easier

how do we make the lifecycle easier? tools
------------------------------------------
* devops tools will make one or more of the three application lifestyle steps easier
* heroku deals with deployment and maintenance
* when you build a tool, you remove the need for users to know how it works
* increase repeatability
* codification of knowledge

Vagrant
-------
* helps with dev part of lifecycle
* anyone in your company can clone out a project (whatever language it is), and have all of the tools they need to work
* virtualbox
* vagrant separates host and guest machines
  * creates a sync between the two machines
  * technology agnostic
* still able to code local on your machine
* consistency: works on linux, osx, windows
* new features
  * ```vagrant share``` makes a public url for your machine
  * ```vagrant connect``` ssh to a remote vagrant machine

Packer
------
* helps with deployment part of the lifecycle (no orchestration)
* other stuff already in the space: chef, docker, capistrano, puppet
* optimize the slow parts of the server by building a server
* devops has been historically against images
  * why?
    * 10 years ago, images were the only way servers were deployed
    * devops people were in a dark corner of the office, alone deploying the images
    * slow iteration
* unfortunately we threw away a lot of the improvements
  * super-fast deployment
  * ops without machine images is like normal applications without binaries (building from source code)
  * if one of the dependencies changes, the deploy without machine images can fail
* can be in a CI and builds vagrant images on successful tests

SERF
----
* helps with maintenance
* decentralized
* high availability

### Membership management ###
* tells you when something leaves a cluster, joins, etc.
* gossip-based membership
  * best example: zombie apocalypse
    * nodes tell each other until they all know
* 200ms from adding a node to the cluster realizing it
  * with crazy-high 10% packet loss, 1000ms
* failure detection
  * historically heartbeats have been used: exponentially increasing the number of connections
  * SERF does this in a better way - all nodes asks just one random person if they're dead

* Devops moves fast: 9 months ago: packer, docker didn't exist
  * be aware of lock in risk
* Hashicorp tries to avoid lock-in

2004-2024 : Two Decades of Web Services, A Retrospective
========================================================

by [Arne Brasseur](https://twitter.com/plexus)

* 1993 - images in browsers, they started worrying if it would scale
  * W3C is formed
* "architectural styles and the design of network-based software architectures" by Ray Fielding - paper that inspired REST interface

properties of www at the start
------------------------------
* low entry barrier
* incremental deployment
* transparent references/identifiers - now referred to as URIs
* extensible
* simple
* anarchic scalability

REST
----
* constraint of a layered system
* each layer knows only about the next layer
* each node has specific responsibilities
* stateless
* client doesn't need to know what kinds of systems are serving

AJAX (2005)
-----------
* client could still not do network requests up until then

Web devs started doing it themselves
------------------------------------
* clients and servers need to both know the references/identifiers
  * the main violation of Ray fielding's thesis

How to adopt hypermedia
-----------------------
* define media types
* define link relations

Benefits of hypermedia
----------------------
* discoverability of the API
* non hardcoded
* change location of benefits
* backwards compatibility
* uniformity, agnosticity across systems - it's just links
* standardization of vocabularies of media types could lead to semantic web-type of linking between systems

Future
------
* non-local linking
* directory services
* aggregators
* vendor-independent client apps

10 Things You Didn’t Know About HTML
====================================

by [Mathias Bynens](https://twitter.com/mathias)

* developer advocate working for Opera
* talk goes over collection of weird stuff that he didn't know about html, css, javascript
* once apon a time, there wasn't such a thing as css
* ```<blink>``` and ```<marquee>``` presentational attributes, shouldn't be using these any more
* deprecated color attributes like bgcolor just got standardized in html5
  * all non-hex values are replaced by zero
  * ```bgcolor="MrT"``` = #000000, blackest black you can get
  * ```bgcolor="chucknorris"``` = the bloodred of chuck's enemies
  * [http://mths.be/bgcolor](http://mths.be/bgcolor) - tool to test it out

"Valid HTML"
------------
* 3 layers of conformance criteria
  * DTD - which elements are supported
    * fails on a placeholder on a input[type="date"]
    * fails: number of table cols incorrect in subsequent rows
* functionality trumps validity

Character references aka html entities
--------------------------------------
* ampersand = &amp;amp; - this is invalid without semicolon
* semicolons - omitting can cause confusing issues
  * just use them

Tags and Elements
-----------------
* end AND start tags are not needed for ```<html>```, ```<body>```, ```<head>``` for valid code

CSS Without HTML
----------------
* with an empty html document, you can still show some stuff on the screen
* ```link``` http header can be used to send link to html document
  * only works in old opera and firefox
*

Font-family names in css
------------------------
* you can omit the quotes around whitespace-separated families

Attribute values
----------------
* you can omit quotes, but watch out
  * kind of like walking around naked in your house
  * sometimes html will be valid but css won't be and won't work

Characters in JS
----------------
* string length attr in js is not really char count
* can account for unicode pairs with punycode libraries


Doctor, Lawyer, Poker Player, Physicist: The Best Engineers We're Not Competing to Hire Yet
===========================================================================================

by [Carina C. Zona](https://twitter.com/cczona)

"Wanted: CS degree or equiv" - you see this every day
-----------------------------------------------------
* the problem is not less people with CS degrees
* if you don't have a degree, how do you know you have the equiv

"Wanted: rock star | ninja | guru"
----------------------------------
* Carina definitely doesn't want a rockstar on their team, touching their code

"Culture fit"
-------------
* fear of discomfort
  * fear of someone new coming in and challenging the status quo
  * the best products can be created just by allowing change
* to be able to define ourselves, we need to be able to seek out:
  * stuff that scares us
  * disruption

Searching for development talent in non-standard industries
-----------------------------------------------------------
* lots of fields have dedication and skills necessary in software engineering:
  * computational biotechnology
  * weaving
  * police officer
  * physical chemistry
  * law
* coding is a work ethic
  * should hire people with this work ethic
  * rock stars have an "admire me" ethic, not work ethic

Coding is archaeological
------------------------
* we hunt around in it, looking for some kind of sense or some old lost civilizations that can help us
* these skills exist in more than just software engineers

Innovative
----------
* a team of a bunch of average people vs a team with an expert within it
  * team with expert comes back with confused, unsure results - limits productivity
    * self-censorship due to the expert
