`const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist')
  }
};`

**Troubleshooting**

1. Run the scaffold project A
1. Run the real project B
1. Compare the directory structure of project A to project B 
1. Copy hidden or missing node_modules from project A to project B
1. Run the binaries in the node_modules/.bin directory directly without npm run or npm run-script to create config files

**References**

* https://nodejs.org/en/blog/npm/npm-1-0-global-vs-local-installation/
* https://docs.npmjs.com/cli/run-script