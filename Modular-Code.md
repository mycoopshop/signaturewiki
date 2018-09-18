<h1>Instructions</h1>
<p>Turn on all options for verbosity in <a href="https://babeljs.io/docs/en/options">webpack</a> and <a href="https://webpack.js.org/configuration/stats/">babel</a>
</p>
<p>Comment out code that you don't need if it is causing errors</p>
<p>Use default imports and exports since webpack and babel fail with poor error messaging when a named import is used with sourcemaps: </p>
<p>
  <a href="https://github.com/webpack/webpack/issues/4423">https://github.com/webpack/webpack/issues/4423</a>
</p>
<p>
  <a href="https://github.com/webpack/webpack/issues/3957">https://github.com/webpack/webpack/issues/3957</a>
</p>
<p> </p>
<p>Use a modular structure like <a href="https://www.npmjs.com/package/highcharts">HighCharts</a> or <a href="https://www.npmjs.com/package/i18next-icu">i18next-icu</a> to avoid the need for destructuring exports</p>
<p>Use jsfiddle, codepen, or plunker to test things such as open source react components. For example:</p>
<p>
  <a href="https://codepen.io/oneezy/pen/jzWjLe">https://codepen.io/oneezy/pen/jzWjLe</a>
</p>
<p>
  <a href="https://jsfiddle.net/boilerplate/typescript">https://jsfiddle.net/boilerplate/typescript</a>
</p>
<p>
  <a href="https://codepen.io/HousewifeHacker/pen/zRRqYe">https://codepen.io/HousewifeHacker/pen/zRRqYe</a>
</p>
<p>
  <a href="https://plnkr.co/edit/R1ECDV?p=info">https://plnkr.co/edit/R1ECDV?p=info</a>
</p>
<p>
  <a href="https://codepen.io/simeg/pen/YppLmO">https://codepen.io/simeg/pen/YppLmO</a>
</p>
<p>
  <a href="https://codepen.io/andytran/pen/jyEPyL">https://codepen.io/andytran/pen/jyEPyL</a>
</p>
<p> </p>
<p>Then map the imports to script tags as follows:</p>
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
<p> </p>
<p>Use the following code for <a href="https://dev.to/luispa/lets-try-react-without-nodejs-3a7">babel and react without node.js</a>:</p>
<pre>&lt;script src="https://unpkg.com/babel-standalone@6.26.0/babel.js"&gt;&lt;/script&gt;
 
&lt;script type="text/babel"&gt;
    var contentNode = document.getElementById('content');
    var component = &lt;h1&gt; Hello World &lt;/h1&gt;; // A simple JSX component
    ReactDOM.render(component, contentNode); // Render the conponent
&lt;/script&gt;</pre>
<p> </p>
<p>Use react as a standard preset: presets:["react"]</p>
<p>Instead of a preset like babel-preset-env, use individual <a href="https://babeljs.io/docs/en/plugins">Babel plugins</a> listed in the verbose output such as:</p>
<ul>
  <li>
    <a href="https://babeljs.io/docs/en/babel-plugin-transform-arrow-functions">https://babeljs.io/docs/en/babel-plugin-transform-arrow-functions</a>
  </li>
  <li>
    <a href="https://babeljs.io/docs/en/babel-plugin-transform-for-of">https://babeljs.io/docs/en/babel-plugin-transform-for-of</a>
  </li>
  <li>
    <a href="https://babeljs.io/docs/en/babel-plugin-transform-destructuring">https://babeljs.io/docs/en/babel-plugin-transform-destructuring</a>
  </li>
  <li>
    <a href="https://babeljs.io/docs/en/babel-plugin-transform-shorthand-properties">https://babeljs.io/docs/en/babel-plugin-transform-shorthand-properties</a>
  </li>
  <li>
    <a href="https://babeljs.io/docs/en/babel-plugin-transform-function-name">https://babeljs.io/docs/en/babel-plugin-transform-function-name</a>
  </li>
</ul>
<p>Use explicit code instead of <a href="https://babeljs.io/docs/en/babel-preset-stage-0">stage0</a>, <a href="https://babeljs.io/docs/en/babel-preset-stage-1">stage1</a>, <a href="https://babeljs.io/docs/en/babel-preset-stage-2">stage2</a>, and <a href="https://babeljs.io/docs/en/babel-preset-stage-3">stage3</a> presets for proposed <a href="https://github.com/tc39/">tc39</a> features such as:</p>
<ul>
  <li>decorators</li>
  <li>class properties</li>
  <li>export-default-from</li>
  <li>null coalescing (??)</li>
</ul>
<p> </p>
<p>Use the copy plugin to move HTML and CSS files rather than loaders, and use <a href="https://www.npmjs.com/package/styled-components">styled-components</a> rather than inline styles</p>
<h1>Related articles</h1>
<p>
