# React App Demo.

> Steps

- Production dependencies

````bash
$ npm init -y
$ npm i express 
$ npm i react react-dom 
$ npm i webpack webpack-cli
$ npm i babel-loader @babel/core @babel/node @babel/preset-env @babel/preset-react
````

- Development dependencies

````bash
$ npm i -D nodemon
$ npm i -D eslint babel-eslint eslint-plugin-react
````

- Test dependencies

````bash
$ npm i -D jest babel-jest react-test-renderer
````

> ESLint config

*.eslintrc.js*

````javascript
module.exports = {
  parser: 'babel-eslint',
  env: {
    browser: true,
    commonjs: true,
    es6: true,
    node: true,
    jest: true,
  },
  plugins: ['react-hooks', 'react'],
  extends: ['eslint:recommended', 'plugin:react/recommended'],
  parserOptions: {
    ecmaVersion: 2018,
    ecmaFeatures: {
      impliedStrict: true,
      jsx: true,
    },
    sourceType: 'module',
  },
  rules: {
    // You can do your customizations here...
    // For example, if you don't want to use the prop-types package,
    // you can turn off that recommended rule with: 'react/prop-types': ['off']
  },
};
````

> Configuring Webpack and Babel

*babel.config.js*

````javascript
module.exports = {
  presets: ['@babel/preset-env', '@babel/preset-react'],
};
````

*webpack.config.js*

````javascript
module.exports = {
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader',
        },
      },
    ],
  },
};
````

$ npm run dev-server
$ npm run dev-bundle

http://localhost:4242/