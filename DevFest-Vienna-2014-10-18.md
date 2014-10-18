[DevFest Vienna 2014](http://www.devfest.at/)
===================

Kick-Ass Documentation Driven Development
-----------------------------------------

by [Floor Drees](https://twitter.com/floordrees)

* we will be really talking about readme-driven development
* but - a readme doesn't replace documentation
* Floor
  * was in berlin, moved back for sektor 5
  * core member of railsgirls summer of code
  * working as a technical documentation writer
* often, we start writing docs when they're done
  * we should start writing requirements before the coding starts
  * avoid feature creep
  * readme-driven development (RDD) brings back an element of product design

### Readme-driven Development

* helps with BDD - behavior- or business-driven development
* helps detect unnecessary complexity early on
* write issues like your documentation
* by being very detailed, this helps other developers work with your product early
* helps to gather feedback early on
* highly visible on GitHub, etc
* easy to provide guidelines collaboration
* pro tip: include in code reviews

### What's a good readme
* write honest, realistic readmes
  * include features that actually already exist
  * air your dirty laundry in your readme
* include lots of code samples
* contributers
* communities available
* license details
* badges for build status

Sentiment Analysis with the Google Prediction API
-------------------------------------------------

by [Marc Edem Aziahome](https://plus.google.com/+MarcEdem)

### Why do we need it

* the application is business intelligence
* visibility into feedback to competitors' products
* analysing global market trends

### Google prediction API

* predict behavior of users
* pattern matching capabilities
* machine learning capabilities
* larger data sets = better results
* minimum data set size

### How to use the prediction API

* harvest data
* label the data
* upload
* let it analyse it and come up with predictions

### Some helpful software to process the data

* Rapidminer
* WEKA

### Sentiment analysis

* text processing with natural language processing
* determines whether tweet is positive or negative

UI Components for Large Amounts of Data
---------------------------------------

by Andreas Hubmer

* two examples using GWT

### GWT

* framework for complex SPAs
* one language - Java
* transports
  * RPC
  * RequestFactory

### UI Component for selecting one user from thousands

* GWT CellTable
* we don't want to send all the data to the clientside
* doing this on the database, and quickly
* storing state
  * option 1: storing state in db
  * option 2: local storage
  * option 3: storage in the url (supported by GWT)

Keeping your Secrets Secret in an Open Source Project
-----------------------------------------------------

by [Gerwin Sturm](https://twitter.com/Scarygami)

* open source is great, but...
* ...do not expose client secrets to the open-source community
  * passwords
  * api keys
  * etc

### Solutions

* not so good: separate repositories
* better: separate this out into a separate file
  * be careful that you don't accidentally commit the secret file to the code
* .gitignore
* git hooks can also be used - but complex when you have more contributers
* Google Web Toolkit solutions available

### Automatic deploy

* this will not work with the file exclusion approach
  * the deploy service won't have your secrets
  * unless you can save the secrets in the environment somehow
    * you need to trust the service in this case

App Distribution and Revenue Models
-----------------------------------

by [Maxim Mai](https://twitter.com/MaximFMai)

* works for Dublin's Online Partnership Group
* Launchpad in Berlin

  * helps early startups focus on what matters
  * quote from [_dkatz](https://twitter.com/_dkatz)
    * "build an app that delivers value"
    * "define target audience"
    * "reach target audience"
    * "generate revenue"

* App revenue models is a jungle

  * Freemium
  * SAAS
  * Pay-to-DL
  * Selling Data
  * Value-Add to existing product

### Understanding your audience

* mid-stage startups "if I track activations and retention rate already, why should I track anything else?"
  * there is lots to track that offers benefit
    * customer segments
    * user journey
    * revenue
    * a/b testing
* example: dating app
  * male users don't have enough contact from females
  * app gets boring
  * one solution: change the algorithm by which the non-contacted males show up for the female users
  * another: offer premium memberships to the males to be more visible
* example: german app with 2M active users without any monatization
  * solution: many ad views in the app, but all disabled
  * tested all different app views with Google Tag Manager without re-releasing app
* more than 90% of app downloads are free downloads
  * 15% of users will make in-app purchases
* this year: 25% in-app purchases, 10% ads
* 2017: 50% IAP, 15% ads
* in a large need to generate user trust before they
* find the sweet spot for pricing for different customer segments for best monatization

### How

* do not do banners - do interstitials instead (full screen ads)
  * do not use interstitials before user gets to content - they will be pissed off
* get users used to splash screens with important information
* video is high impact
* cache your ads

### Mediation

* try to diversify between different ad networks
* prices for each impressions
  * format and medium
  * country
  * really important: how many times an ad was shown to a specific user per day
    * build a counter in your app for how many ad impressions for a specific user

### Global Targeting

* instead of just targeting locally, you can maximize your reach if you:
  * think outside of the local box
  * think how international users will use it

### App Design

* algorithms for featuring in the play store use these criteria
  * don't break the design guidelines
  * optimize for many tablet sizes
  * only ask for permissions you really need
  * stay above 4.0 stars in play store reviews
* creative ways of asking users for feedback
  * "awesomeness" slider - an alternate interface for the play store reviews
* use alpha and beta testers
* case study: recipes startup - could a freemium model work?
  * found a solution with testing testing testing
* viral - be careful
  * can be very powerful
* app indexing
* cross-promotion of your own apps
  * bartering - promotion in a group

### Sustainable revenue models

* re-engaging / retaining users is more sustainable than acquiring new users

