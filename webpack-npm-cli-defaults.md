`
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist')
  }
};
`

**References**

* https://nodejs.org/en/blog/npm/npm-1-0-global-vs-local-installation/
* https://docs.npmjs.com/cli/run-script