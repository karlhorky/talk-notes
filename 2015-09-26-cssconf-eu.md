# CSSconf EU

## The Front-End Revolution

by [Claudina Sarahe](https://twitter.com/itsmisscs)

- what is revolutionary? something that disrupts normal dynamics and changes everything around it
- as our devices have taken over and more of the world comes online, we need more people involved in the community
- many new tools
- transforming our lives as developers
- they can turn our capabilities into opportunities
- revolutions don't happen when we adopt new technologies
- they happen when we adopt new behaviors

### Fogg Behavior Method

- method for developing persuasive technologies
- computers may be actually able to modify and change what people do

#### What causes behavior

- motivation
  - money
  - freedom
- ability
  - time
  - skills
- trigger
  - ex. an article that you read that inspires you to do something
  - requirements:
    - we have to notice them
    - we have to associate this trigger with a target behavior

### Tooling history

- new JS frameworks in 2000s started a revolution in web dev
  - trying to make the APIs of the web simpler
- jQuery (2006) succeeded because of
  - simplicity
  - good documentation
  - invitation to contribute
- jQuery's first plugin very early on
- CSS was having its renaissance at this time
  - 960px grid frameworks
  - IE 6-9
  - CSS3 was coming with many new features
  - SMACSS, OOCSS, BEM were developed
  - Sass, Less, etc with CSS preprocessors
- Sass
  - won 2014 .Net game changer award
  - one article: 66% of devs in one study using Sass
  - now influencing CSS
    - variables (custom properties)
    - mixins
    - grids
    - blend modes
- our tools are opening up new opportunities for us
- there are no longer these large institutions holding up progress in the space
- collective participation + collective action = required ingredients for change

### Small world networks

- small world networks: many nodes that are connected together
- resistent to damage
- disseminate information very well
- our frontend networks enjoy this resilience
- this will only come through participation
- maybe we can use these same techniques and connections to change things in other networks like our cities

- "changes of scale mean that improbable theories become likely and that unlikely events become certainties"

## Photoshop is Dead!: Editing Images in CSS

by [Una Kravets](https://twitter.com/una)

- frontend developer at IBM design team

### Photoshop

- average loading time of 33s
- responsive design? LOL
- expensive

### Chrome

- filters in CSS
  - grayscale
  - blur
  - drop shadow
  - etc
- blend modes
  - darken
  - lighten
  - contrast
  - multiply
  - etc
- many more things are coming

### Live-world Examples

- Polygon
- XOXO conference

### Capabilities

- with a bit of creativity and analysis, you can recreate Photoshop's effects in the browser

## It's All Just Functions And Variables

by [Michael Mifsud](https://twitter.com/xzyfer)

- frontend dev at 99 designs
- core contributor to libsass
- learned many many languages and frameworks
- many programming languages based on C (C-Style languages)
  - JavaScript
  - PHP
  - Sass
- the "real programmer"
  - what is "real programming"? are languages like CSS also real programming?
- dunning-kruger effect
  - "a cognitive bias wherein relatively unskilled individuals suffer from illusory superiority, mistakenly assessing their ability to be much higher than is accurate"
  - "conversely, highly skilled individuals may underestimate their relative competence, erroneously assuming that tasks that are easy for them also are easy for others"
- 2014: the first iteration of libsass - porting Sass to C++

### Diving in to C++

- OMG scary
- "Real programming"
- useful techniques
  - CPDD: Copy Paste Driven Development
  - CEDD: Compiler Error Driven Development
- first versions were horribly unperformant

## [The Missing Slice](http://leaverou.github.io/missing-slice)

by [Lea Verou](https://twitter.com/leaverou)

- Lea: CSS WG invited expert
- Lea: human computer interaction research work
- example: pie charts: they're everywhere
- but difficult and complicated to define in CSS

### Hallmarks of Good CSS Solutions

- flexibility
  - how do we modify the code later?
- maintainability
  - how much code?
  - extra elements?
  - straightforward?
- extensibility
  - can we add things to the solution later?

## I Don't Want To Be On Facebook All Day!

by [Horia Dragomir](https://twitter.com/hdragomir)

- Messenger.com - full page react app to send / receive messages
- why build it? corporate blocking, cool to build

### How does Facebook frontend?

- use modules, small components
- scoped, encapsulated css
- public keyword in class names to mark styles as useable by other modules
- CSS auto-packaged and required
- human mode: reading / writing software
- machine mode: machine when it executes your code
- static transforms allows you to get the best of both modes
  - ex. vendor prefixes
- delivery architecture: only deliver the needed vendor prefixes for each browser
- no units for 0
- munging
  - readable names for humans
  - efficient names for machines
- CSS is mostly vanilla, with exceptions for static transforms
  - CSSConstants are also included for variables (var() syntax)
- style-agnostic components
  - container elements without styles
  - these contain other elements with styles

### Messenger.com

- no support for old browsers
- wanted to use flexbox, but could not reproduce design with it
  - started by using the battle-tested <Layout />
  - ended up debugging it a bit more and it turned out to be the static transforms that were causing errors
- components like px, but the design was responsive and would work better with percentages
- right panel should automatically close when not enough space
- Messenger.com was able to take the original buttons from Facebook with all the accessibility improvements
  - first secondary domain running with facebook components

## [Interoperable CSS](https://glenmaddern.com/slides/interoperable-css-eu)

by [Glen Maddern](https://twitter.com/glenmaddern)

- Stoic philosophy: "all this has happened before, all this will happen again"
- Sept 2008
  - 70% of world using IE 7
  - heavy use of window-level namespacing in browsers
    - everything runs in this global soup and you just need to carve off a piece for yourself to work in
- ServerJS in 2009
- Kevin Dangoor: "JavaScript needs a standard way to include other modules and for those modules to live in discreet namespaces. There are easy ways to do namespaces, but there's no standard programmatic way to load a module (once!)."
- Kevin Dangoor: "Server-side JavaScript is very fragmented. A script that accesses files can't be used without modification on both rhino and v8. Spidermonkey and JavaScriptCore can't both load in additional modules in the same way."
- this is similar to Sass/Less now
  - not interoperable
- Node.js Feb 2009
  - CommonJS July 2009
  - Node.js and commonJS had different visions, node's version won
  - module system moved namespacing to the filesystem

### How does this relate to CSS?

- single global context -> module system and package ecosystem
- Browserify: you can change the human interface of a language without needing to change the machine interface
- Is this possible with CSS?
- yes, with interoperable CSS
  - :import and :export directive, rest of file is global
  - built to support css modules
- @vjeux's problems with css
  - global namespace
  - dependencies
  - dead code elimination
  - etc
- CSS in JS proposed as option
  - Radium *
  - React
  - etc
  - CSS community loudly unhappy
### CSS Modules
- helping you maintain much of current knowledge of CSS
- good design should lead you to good practice
- what would make css easier for humans?
- Why no success before? many other solutions focused on just Isolation or Reuse
  - isolation: components -> styles, Bem
  - reuse first: styles -> components, OOCSS, small filesizes, difficult for teams, change paralysis

#### Isolation

- if you want to target specific element, you can
  - write very specific selectors
  - write super long names (like BEM)
    - this looks like JS 2008
- CSS Modules solution: local by default
  - class names abstracted to paths
  - in these files, you can use whatever short local names that make sense (ex. .normal or .error in buttons/submit.css)

#### Abstractions

- good abstractions save you from cognitive load

#### Multi-file composition

- because each file is isolated, you can't reference other files
- with composes property and other classes from other files
- allows you to compose atomic classes by mixing in other styles
- this solves reuse

## Emotion Through CSS

by [Tammy Lister](https://twitter.com/karmatosed)

- code psychology is exciting
- how can we create experiences to connect with others
- emotion: essential part of being human
  - range of emotion is incredible
  - we assign emotion to inanimate objects: ex. sad, grumpy laptop when it can't boot
  - without emotions, objects can feel a bit uneasy
  - animals feel emotions too
- pepper: social robot
- robot seal: elicits emotional response
  - with sounds and actions
- humans need emotional connection
  - like primates needing a hug
- emotions are feelings of the mind
- emotions consist of three parts
  - physiological response
  - behavior or expressive response
  - subjective experience
- animation touches our emotions

### The web

- in contrast, interaction is cold
- the feeling is web is for robots, rather than humans
- how do you show emotion just through an interface
- robots: what happens when you have no face?

### What can we do?

- even simple animations can show a bit of emotion
- timing is critical for conveying emotion or personality
- exaggeration: can elicit emotional response
  - careful to not overuse

### Engaging users

- emotional experiences create connections with users
- users kind of bond with interfaces as they use them
- small little touches like animating the eyes on characters

### CSS Animations

- can do this engagement with CSS animations
- playful interfaces for games
- animations can be used in smaller interactions as well
  - slack: the emoji picker
  - Codepen: three levels of notification
    - first a little color bar
    - then highlighting the button through change in size
    - then finally a notification bar
  - Codepen: heart animation on like

### Adding a personality to buttons

- happy button: taking cues from minions
  - jumping up and down intermittently, and on hover constant jumping
- angry button
- sad button: cues from pikachu
  - slow heaving motion
- coughing button
- zen inputs
  - quietly doing its own thing
  - moving, but not noticably

### Invisible animations

- when animations are good, you don't notice them
- it's about adding to the experience subconsciously
- animation films, studio ghibli, etc

### Giving feedback to the user

- interface elements can be impatient or angry or happy
- easier to create a connection with the users

## [Developing for Localization: CSS Techniques To Get Your Message Across To The World Wide Web](https://katiek2.github.io/localization/)

by [Katie Kurkowski](https://twitter.com/katiek2)

- localization is tough with fixed designs
- localization: not just switching the text and language
  - culture changes: Pixar changed the vegetable in one of their films for Japan since the other vegetable was culturally more reviled
  - changing the units
  - changing the quotes
  - etc

### example: text embedded in image

- text should stay text
- don't hardcode in the image
- boxes need to expand and contract (german is typically longer as english, japanese typically shorter)

### example: headline and jumbotron

- line breaks and orphans a problem
- would be nice: cross-browser orphan management, also for non-text elements
- can do at least something now: hiding breaks on different breakpoints

### example: groups of boxes: markup

- differing title, content and box heights that need to be all aligned
- 2 nested flexboxes with different flex directions

### Tips

- be careful with using text-transform in CSS - they can create strange anomalies in non-roman characters
- plan early on for the text size to vary
- increased device font size
- dealing with cmses

## Enhancing responsiveness with Flexbox

by [Zoe Mickley Gillenwater](https://twitter.com/zomigi)

- Zoe: from booking.com in Amsterdam
- at booking.com
  - 802k properties
  - 42 languages
  - 54 currencies
  - need flexible designs for these variations
- %, em/rem, vw/vh helpful, but not perfect
- relative units of measurements are a best guess at the ideal, but still a guess
- any unit of measurement is going to be an approximation
- flexbox gets closer to the ideal (designing without units)

### example: job search @ guardian (responsive breakpoints with %s)

- 2 opportunities for progressive enhancement
- menu text can be cut off
- button can be too big for the content
- you cannot control these values
- if you use flex property instead, it will grow and shrink if you tell it that it can
  - flex: none - size to content exactly
  - flex: auto - fill remaining space
- you can fix vertical alignment and height of elements with flexbox as well
- progressive enhancement for browsers that support flexbox

- content-driven breakpoints are better than device-based, but they still are a decision and have weaknesses

### example: booking.com contact form

- responsive layout without media queries (with flexbox)
- inputs are positioned next to each other on larger screens, in a column on smaller screens
  - `flex: 1 0 40%;`
  - this is:
    - `flex-grow: 1;` give it 1 share of any extra width on its line
    - `flex-shrink: 0;` - don't shrink smaller
    - `flex-basis: 40%;` - start field at 40%

### example: booking.com map info windows

- label should be displayed left of the button
- but this space is not always available
- this label should be dropped down to the next line if the space is not available
- flexbox to the rescue again

### example: blog

- right-floated label wraps to next line
- with floating (without media queries), label is right aligned on new line - awkward
- if you use flexbox, you can left align the label on the new line

### rearrangement of visual and flow ordering

- with the `order` property
- tip: reorder only for good, not for evil
- html order still needs to be logical for the content

### example: guardian.com

- shuffling stories around in the wide view
  - they're not using `order` property

### sage advice

- flexbox requires a mental shift in how you think about and approach layout
- RWD is not binary - it's a continuum
- flexbox can help make your site more responsive than it already is
