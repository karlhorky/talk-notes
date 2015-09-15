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

