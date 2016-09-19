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

## Riot.js

by Christian Niederreiter
