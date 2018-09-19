## Instructions

### Debugging
* Turn on all options for verbosity in <a href="https://babeljs.io/docs/en/options">webpack</a> and <a href="https://webpack.js.org/configuration/stats/">babel</a>

* Comment out code that you don't need if it is causing errors</p>

* Use default imports and exports since webpack and babel fail with poor error messaging when a named import is used with sourcemaps:

1.  <a href="https://github.com/webpack/webpack/issues/4423">https://github.com/webpack/webpack/issues/4423</a>

2.  <a href="https://github.com/webpack/webpack/issues/3957">https://github.com/webpack/webpack/issues/3957</a>

### Organization

* Use a modular structure like <a href="https://www.npmjs.com/package/highcharts">HighCharts</a> or <a href="https://www.npmjs.com/package/i18next-icu">i18next-icu</a> to avoid the need for destructuring exports</p>

* Use jsfiddle, codepen, or plunker to test things such as open source react components. For example:

1.  <a href="https://codepen.io/oneezy/pen/jzWjLe">https://codepen.io/oneezy/pen/jzWjLe</a>

1. <a href="https://jsfiddle.net/boilerplate/typescript">https://jsfiddle.net/boilerplate/typescript</a>

1. <a href="https://codepen.io/HousewifeHacker/pen/zRRqYe">https://codepen.io/HousewifeHacker/pen/zRRqYe</a>

1. <a href="https://plnkr.co/edit/R1ECDV?p=info">https://plnkr.co/edit/R1ECDV?p=info</a>

1. <a href="https://codepen.io/simeg/pen/YppLmO">https://codepen.io/simeg/pen/YppLmO</a>

1. <a href="https://codepen.io/andytran/pen/jyEPyL">https://codepen.io/andytran/pen/jyEPyL</a>

* Then map the imports to script tags as follows:

<table class="wrapped">
  <colgroup>
    <col/>
    <col/>
  </colgroup>
  <tbody>
    <tr>
      <th>import</th>
      <th>script</th>
    </tr>
    <tr>
      <td>import React from 'react'</td>
      <td>
        <a href="https://unpkg.com/react@16.0.0/umd/react.production.min.js">https://unpkg.com/react@16.0.0/umd/react.production.min.js</a>
      </td>
    </tr>
    <tr>
      <td>import ReactDOM from 'react-dom'</td>
      <td>
        <a href="https://unpkg.com/react-dom@16.0.0/umd/react-dom.production.min.js">https://unpkg.com/react-dom@16.0.0/umd/react-dom.production.min.js</a>
      </td>
    </tr>
    <tr>
      <td>import moment from 'moment'</td>
      <td>
        <a href="https://unpkg.com/moment@2.22.2/moment.js">https://unpkg.com/moment@2.22.2/moment.js</a>
      </td>
    </tr>
  </tbody>
</table>

### Prototyping

Use the following code for <a href="https://dev.to/luispa/lets-try-react-without-nodejs-3a7">babel and react without node.js</a>:
<pre>&lt;script src="https://unpkg.com/babel-standalone@6.26.0/babel.js"&gt;&lt;/script&gt;
 
&lt;script type="text/babel"&gt;
    var contentNode = document.getElementById('content');
    var component = &lt;h1&gt; Hello World &lt;/h1&gt;; // A simple JSX component
    ReactDOM.render(component, contentNode); // Render the conponent
&lt;/script&gt;</pre>

### Configuration

* Use react as a standard preset: presets:["react"]

* Instead of a preset like babel-preset-env, use individual <a href="https://babeljs.io/docs/en/plugins">Babel plugins</a> listed in the verbose output such as:

*  <a href="https://babeljs.io/docs/en/babel-plugin-transform-arrow-functions">https://babeljs.io/docs/en/babel-plugin-transform-arrow-functions

* <a href="https://babeljs.io/docs/en/babel-plugin-transform-for-of">https://babeljs.io/docs/en/babel-plugin-transform-for-of</a>

* <a href="https://babeljs.io/docs/en/babel-plugin-transform-destructuring">https://babeljs.io/docs/en/babel-plugin-transform-destructuring</a>

* <a href="https://babeljs.io/docs/en/babel-plugin-transform-shorthand-properties">https://babeljs.io/docs/en/babel-plugin-transform-shorthand-properties</a>

* <a href="https://babeljs.io/docs/en/babel-plugin-transform-function-name">https://babeljs.io/docs/en/babel-plugin-transform-function-name</a>

* Use explicit code instead of <a href="https://babeljs.io/docs/en/babel-preset-stage-0">stage0</a>, <a href="https://babeljs.io/docs/en/babel-preset-stage-1">stage1</a>, <a href="https://babeljs.io/docs/en/babel-preset-stage-2">stage2</a>, and <a href="https://babeljs.io/docs/en/babel-preset-stage-3">stage3</a> presets for proposed <a href="https://github.com/tc39/">tc39</a> features such as:

1. decorators
1. class properties
1. export-default-from
1. null coalescing (??)

### Reusability

* Use the [copy webpack plugin](https://stackoverflow.com/questions/45036810/webpack-copying-files-from-source-to-public-using-copywebpackplugin) to move HTML and CSS files rather than the loaders in development mode, use the [file-loader](https://stackoverflow.com/questions/52110999/webpack-file-loader-configuration-for-static-images) to inline images, the [style-loader](https://css-tricks.com/css-modules-part-2-getting-started/) to inline styles, the [postCSS plugin](https://simonsmith.io/using-webpack-to-build-react-components-and-their-assets/) to handle CSS imports, and use the [extract text plugin](https://github.com/webpack-contrib/extract-text-webpack-plugin) to combine the styles with the design language CSS in production mode

* Use <a href="https://www.npmjs.com/package/styled-components">styled-components</a> rather than inline styles

### References

* [Webpack and npm for Simple Java 8 Web Apps](https://www.stubbornjava.com/posts/webpack-and-npm-for-simple-java-8-web-apps) 

* [Webpack a Spring Boot App With Instant Page Refresh](https://medium.com/@grantminer/webpack-a-spring-boot-app-with-instant-page-refresh-5d051a09d26f)

* [How to Develop a WordPress Plugin Using Webpack 3 & React (Part 1)](https://deliciousbrains.com/develop-wordpress-plugin-webpack-3-react/)

* [Fast Front End Development Cycle with Spring Boot | vorba.ch](https://vorba.ch/2016/fast-spring-boot-development-cycle.html)

* [Spring Boot and Vue.js](https://randyyaj.github.io/post/20161129_vue_spring/)