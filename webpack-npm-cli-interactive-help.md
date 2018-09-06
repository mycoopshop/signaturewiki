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

**Defensive Programming**
* https://basarat.gitbooks.io/typescript/docs/tips/defaultIsBad.html
* https://hackernoon.com/import-export-default-require-commandjs-javascript-nodejs-es6-vs-cheatsheet-different-tutorial-example-5a321738b50f
* https://news.ycombinator.com/item?id=13308948

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
* http://justjs.com/posts/npm-link-developing-your-own-npm-modules-without-tears
* https://medium.com/@alexishevia/the-magic-behind-npm-link-d94dcb3a81af
* https://60devs.com/simple-way-to-manage-local-node-module-using-npm-link.html
* https://www.npmjs.com/package/didyoumean2
* https://www.linux.com/news/parsing-arguments-your-shell-script
* https://stackoverflow.com/questions/23016298/getopt-like-behavior-in-powershell
* https://rosettacode.org/wiki/Parse_command-line_arguments#PowerShell
* https://oclif.io/
* https://github.com/webpack-contrib/sass-loader/issues/484
* https://github.com/webpack/webpack/issues/2704
* https://github.com/webpack-contrib/sass-loader/issues/272
* https://github.com/webpack-contrib/css-loader/issues/216
* https://css-tricks.com/introduction-webpack-entry-output-loaders-plugins/
* https://babeljs.io/docs/en/next/presets.html
* https://babeljs.io/blog/2015/10/31/setting-up-babel-6
* https://babeljs.io/docs/en/v7-migration
* https://medium.freecodecamp.org/how-to-solve-webpack-problems-the-practical-case-79fb676417f4
* https://github.com/chimurai/http-proxy-middleware#options
* https://github.com/webpack/webpack-dev-server/issues/147
* https://stefanscherer.github.io/windows-docker-workshop/#1

# Migration
* https://webpack.js.org/guides/asset-management/
* https://medium.com/@yangnana11/how-to-run-and-build-webpack-b28a7ae612db
* https://deliciousbrains.com/npm-build-script/

# Benchmarking
* https://webpack.js.org/api/stats/
* https://github.com/webpack-contrib/webpack-bundle-analyzer
* https://webpack.js.org/configuration/performance/
* https://webpack.js.org/configuration/other-options/

# Optimization
* https://webpack.js.org/configuration/optimization/
* https://webpack.js.org/configuration/devtool/
* https://webpack.js.org/guides/caching/
* https://webpack.js.org/concepts/mode/

# Internals
* https://babeljs.io/blog/2018/07/27/removing-babels-stage-presets