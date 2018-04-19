    const path = require('path');

    module.exports = {
      entry: './src/index.js',
      output: {
        filename: 'bundle.js',
        path: path.resolve(__dirname, 'dist')
      }
    };


**Troubleshooting**

1. Run the scaffold project A
1. Run the real project B
1. Compare the directory structure of project A to project B 
1. Copy hidden or missing node_modules from project A to project B
1. Run the binaries in the node_modules/.bin directory directly without npm run or npm run-script to create config files

**References**

* https://nodejs.org/en/blog/npm/npm-1-0-global-vs-local-installation/
* https://docs.npmjs.com/cli/run-script
* https://stackoverflow.com/questions/38153857/bundle-angular-2-app-using-umd-bundles-not-building-vendor-bundle
* https://viblo.asia/p/tuning-webpack-production-environment-bWrZneYQKxw
* https://github.com/webpack/webpack/tree/master/examples
* https://github.com/webpack/docs/wiki/configuration
* https://css-tricks.com/introduction-webpack-entry-output-loaders-plugins/
* https://vegibit.com/vue-cli-webpack-simple-tutorial/
* https://developers.google.com/web/tools/workbox/modules/workbox-webpack-plugin
* https://auth0.com/blog/webpack-4-release-what-is-new/
* https://legacy.gitbook.com/book/wohugb/webpack/details
* https://what-problem-does-it-solve.com/webpack/production.html
* https://engineering.wingify.com/posts/migrating-towards-yarn-webpack/
* https://medium.com/@rajaraodv/webpack-the-confusing-parts-58712f8fcad9
* https://codeburst.io/maybe-dont-globally-install-that-node-js-package-f1ea20f94a00
* https://firstdoit.com/no-need-for-globals-using-npm-dependencies-in-npm-scripts-3dfb478908
* https://blog.angularindepth.com/this-will-make-you-more-efficient-at-debugging-wepback-unspecified-build-errors-6392850caed9
* https://www.slideshare.net/trueter/how-to-make-your-webpack-builds-10x-faster
* https://medium.com/@vasylstashuk/optimizing-webpack-build-performance-73f2cf0bb176