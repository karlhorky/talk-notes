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
* [https://github.com/macabre/phantomas](https://github.com/macabre/phantomas)

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