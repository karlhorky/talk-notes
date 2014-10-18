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


