## Basic npm

Run npm ping (https://docs.npmjs.com/cli/ping) to test the connection to the URL of the registry

Run npm install webpack@3 to download the main dependency, such as webpack@3

Run npm view webpack to see the release date of webpack@3

Run npm view babel-loader (https://docs.npmjs.com/cli/view) to view the babel-loader release dates

Run npm install babel-loader@x.x.x where x.x.x is the version number with the closest release date to webpack@3

Run npm explore webpack to customize the webpack package.json in a subshell (https://docs.npmjs.com/cli/explore)

Run npm docs webpack (https://docs.npmjs.com/cli/docs) to view the webpack docs

Run npm edit (https://docs.npmjs.com/cli/edit) to update the package.json with the peer dependencies

Run npm prune (https://docs.npmjs.com/cli/prune) to remove any unused packages

Run npm dedupe (https://docs.npmjs.com/cli/dedupe) to remove any duplicate packages

Run npm rebuild (https://docs.npmjs.com/cli/rebuild) to rebuild all the packages

Run npm shrinkwrap (https://docs.npmjs.com/cli/shrinkwrap) to lock down all the package files by version number

Check the troubleshooting page (https://docs.npmjs.com/troubleshooting/common-errors) for any error messages

## Basic Webpack

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
* https://github.com/webpack/webpack/tree/master/examples

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
* https://github.com/TotallyInformation/node-red-contrib-uibuilder/wiki/Building-app-into-dist-folder-using-webpack
* https://css-tricks.com/combine-webpack-gulp-4/
* https://www.sitepoint.com/bundle-static-site-webpack/
* https://vijayt.com/post/scaffolding-react-web-app-webpack-2/
* http://ramkulkarni.com/blog/setting-up-webpack-babel-reactjs/

# Migration
* https://github.com/webpack-contrib/copy-webpack-plugin#this-doesnt-copy-my-files-with-webpack-dev-server
* https://codefor.life/everything-i-need-to-know-about-javascript-tools/
* https://www.slideshare.net/loige/unbundling-the-javascript-module-bundler-codemotion-rome-2018
* https://www.jamasoftware.com/blog/upgrade-node-module-right-way/
* https://www.codementor.io/elliotaplant/understanding-javascript-module-resolution-systems-with-dinosaurs-il2oqro6e
* https://webpack.js.org/guides/asset-management/
* https://medium.com/@yangnana11/how-to-run-and-build-webpack-b28a7ae612db
* https://deliciousbrains.com/npm-build-script/
* https://markus.oberlehner.net/blog/goodbye-webpack-building-vue-applications-without-webpack/
* https://vuejsdevelopers.com/2017/12/04/webpack-intro-vue-js/
* https://medium.com/webpack/unambiguous-webpack-config-with-typescript-8519def2cac7
* https://medium.com/@dferber90/enabling-assets-for-server-side-rendering-in-webpack-a843a5ebeb0c

# Legacy Mapping
* https://www.npmjs.com/package/xslt-template-loader
* https://www.npmjs.com/package/svg-url-loader
* https://www.npmjs.com/package/freemarker-parser

# Issues
* https://github.com/webpack/webpack/issues/6617
* https://webpack.js.org/guides/author-libraries/
* https://github.com/babel/babel/pull/7980
* https://github.com/systemjs/systemjs/issues/450
* https://github.com/webpack/webpack/issues/1747
* https://github.com/babel/babel-loader/issues/149
* https://github.com/webpack/webpack/issues/5433
* https://github.com/webpack/webpack/issues/554
* https://github.com/webpack/webpack/issues/2937
* https://github.com/webpack/webpack/issues/6796
* https://github.com/webpack/webpack.js.org/issues/68
* https://github.com/webpack/webpack/issues/4160
* https://github.com/YahooArchive/strip-loader/issues/24

# Mocking
* https://www.npmjs.com/package/mock-webpack-plugin

# Specs
* https://github.com/defunctzombie/package-browser-field-spec
* https://github.com/webpack/webpack/issues/520

# Benchmarking
* https://webpack.js.org/api/stats/
* https://github.com/webpack-contrib/webpack-bundle-analyzer
* https://webpack.js.org/configuration/performance/
* https://webpack.js.org/configuration/other-options/

# Plugin Dev
* https://github.com/evcohen/accessibility-webpack-plugin

# Aliasing
* https://medium.com/@justintulk/solve-module-import-aliasing-for-webpack-jest-and-vscode-74007ce4adc9
* http://xabikos.com/2015/10/03/Webpack-aliases-and-relative-paths/

# Optimization
* https://webpack.js.org/configuration/optimization/
* https://webpack.js.org/configuration/devtool/
* https://webpack.js.org/guides/caching/
* https://webpack.js.org/concepts/mode/
* https://webpack.js.org/configuration/configuration-languages/
* https://webpack.js.org/configuration/watch/
* https://blog.benestudio.co/remove-console-log-statements-from-production-javascript-apps-7376adc89c7a
* https://github.com/webpack/webpack/issues/6586

# Internals
* https://babeljs.io/blog/2018/07/27/removing-babels-stage-presets
* https://webpack.js.org/configuration/node/