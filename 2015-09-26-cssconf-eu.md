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
