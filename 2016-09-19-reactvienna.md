# React Vienna September Meetup feat. Stahlstadt.js

2016-09-19 in Linz, Austria

## Internationalization in React

by [Ognian Tschakalov](https://twitter.com/ogi_it/)

- if you google, you find yahoo's react-intl
  - appears very complex
- is there a different option?
  - yes, there are other options, but they are developer-centric
  - not translator-friendly; translators use CAT (Computer-Aided Translation) tools which have specific requirements
- need something that is developer- and translator-friendly
- this is what Ognian did
- he used yahoo's react-intl
- he used a babel plugin: `babel-plugin-react-intl`
  - parses every react component and extracts the messages
  - he wrote a webpack plugin (`Ognian/react-intl-webpack-plugin`) which combines the messages output into one file
    - need to use Ognian's version of the babel loader for now
  - wrote Ognian/reactIntlJson-loader to lo
- using Ognian's plugin, you can use memsource.com for free with a single json file

## Draft.js

by [Nik Graf](https://twitter.com/nikgraf)

- Nik: in the last year worked on three open source projects
  - Carte Blache
  - DraftJS Plugins
  - Belle
- Nik working at Serverless now
- Draft.js is a wysiwyg component that Facebook developed
  - they're using it in production in comments and Notes
  - it creates actual DOM elements for content

### How does draft.js do this?

- there is an html property called contenteditable
  - this generates inconsistent DOM between browsers
  - looked down on in the industry for these inconsistencies and bad API
- Draft.js does it differently
  - maps the content to an immutable data structure
    - you don't want to put html into your database for security

### How can we use draft.js?

- import it into your project and define a starting state and onChange callback in your component
- Draft.js provides the basic low-level building blocks for creating powerful editors
- can create your own blocks for custom elements like sticker images
- with decorators, you can enhance existing content (like adding a hash to a hashtag)
- knowledge required and complex to build newfeatures with Draft.js

### Draft.js plugins

- Nik and team created Draft.js Plugins to make it easier to add features to editors
  - hashtag plugin
  - image stickers plugin
  - facebook friend mentions plugin

## Riot.js

by Christian Niederreiter
