

## Minimal Setup React

#### After cloning this repository, use the command:

### `yarn install` or `npm install` 

#### This command will download and install all dependencies in your project. Then, use the following command to start an application: 

### `yarn start` or `npm start`


Configuration Web Pack
Our Webpack config (webpack.config.js) is as simple as this:

```
const path = require('path')

module.exports = {
  entry: './src/index.js',

  output: {
    path: path.resolve('dist'),
    filename: 'bundle.js',
  },

  module: {
    rules: [
      {
        test: /\.js$/,
        loader: 'babel-loader',
      },
    ],
  },
}
```

Main component:
```
import React from 'react'
import ReactDOM from 'react-dom'
import App from './App'

ReactDOM.render(<App />, document.getElementById('app'))
```
Babel
The Babel loader will parse all files with .js extension and convert the JSX tags and ES2015 code to valid ES5. We need to enable these two transformations on the Babel config file (.babelrc), like this:

```
{
  "presets": [ "es2015", "react" ]
}
```
## index.html
```
<!DOCTYPE html>

<html>
  <head>
    <title>React</title>
  </head>
  <body>
    <div id="app"></div>
    <script src="dist/bundle.js"></script>
  </body>
</html>
```