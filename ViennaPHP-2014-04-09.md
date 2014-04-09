Vagrant in Two Minutes
======================

by [Sebastian Göttschkes](https://twitter.com/sgoettschkes)

* make configuration easier
* everyone using the same configuration
* provisioners
  * installing apache, php, etc
  * ex. Chef or Puppet
  * without sshing in
* vagrant up to start the machine
* vagrant ssh to connect
* source files are on your local machine - synced with nfs or shared folders

Web Performance 101
===================

by [Michael Kröll](https://twitter.com/pierlopone)

why does it matter
------------------
* performance = money (study by amazon: every 100ms caused an increase in revenue)
* reduce costs
* be green
* slow pages can negatively affect brand image
* faster pages are, better they rank in search engines
* do better against competitors

what affects it
---------------
* device, browser, net activity
* how fast your backend / databases respond

how to measure
--------------
* google page speed
* yslow
* webpagetest.org
* [https://github.com/macbre/phantomas](https://github.com/macbre/phantomas)

best practices
--------------
* watch your front-end performance in popular browsers
* backend problems can be much more crippling than frontend issues
* mix of synthetic and user tests
* pay attention to the different set of rules that you have on the growing mobile audience
  * Spiegel online has almost 50% mobile
* include in:
  * deploy
  * monitoring
  * logging
* [http://www.perfplanet.com](http://www.perfplanet.com)

low hanging fruit
-----------------
* reduce http reqs
* reduce number of bytes transferred
* simpler DOM
* domain sharding (assets on different subdomain so that cookies don't need to be transferred)

Apache vs. Nginx
================

by [Jakob Oberhummer](http://www.meetup.com/viennaphp/members/96722012/)

* a web server is
  * a server running on a port that receives and outputs http, processing in the middle
* common web servers
  * apache
  * nginx
  * lighthttp
  * Microsoft IIS
* underdogs
  * litespeed
  * abyss
  * boa
  * cherokee
  * mongoose
  * more
* language-specific
  * Java: Tomcat, Jetty, Jo!, many more
  * Ruby: Thin, WeBrick, Rack, puma
  * others: simplehttprequesthandler (python), boost (c++), connect (node), PHP-FPM
* history
  * Apache:
    * 1995 first release
    * 8 devs
    * 53% of market
  * IIS
    * 1995
    * EMWAC
    * thread-based
  * litespeed
    * 2002
    * George Wang
  * Nginx
    * 2002
    * igor sysoev
    * low memory consumption, high output
  * LightHTTP
    * 2003
    * Jan Kneschke
    * is it possible to handle 10k connections at once
  * cherokee
    * 2011
    * many contributers on github
* types
  * thread based: one thread for each client
  * thread pool: better handling of threads
  * event driven: client sends req to async web server which sends to queue, which sends to a req handler and on to a callback service
    * easier to control load

some best practice tweaks
-------------------------
* compress your data
* cache as much as possible
* reduce redundant requests
* load balance if possible

### Apache 2.2 ###
* reduce keep-alive (cpu/requests)
* reduce TTL of a thread (memory)

### Nginx ###
* use internal load balancing
* ifs are bad

Grunt.js for developers
=======================

by [Florian Eckerstorfer](https://twitter.com/Florian_)

* what is grunt?
  * a task runner
  * like phing, make, ant, etc
  * written in js, not anything to do with the browser
* Gruntfile.js - configuration for tasks
* tasks for stuff like
  * cssmin - css minification
  * phpunit and symfony2
* backend and frontend tasks
* async - watching for changes and executing tasks
* totally plugin based