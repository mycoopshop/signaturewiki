## Basic npm

Run npm ping (https://docs.npmjs.com/cli/ping) to test the connection to the URL of the registry

Run npm install webpack@3 to download the main dependency, such as webpack@3

Run npm view webpack to see the release date of webpack@3

Run npm view babel-loader (https://docs.npmjs.com/cli/view) to view the babel-loader release dates

Run npm install babel-loader@x.x.x --save-dev, where x.x.x is the version number with the closest release date to webpack@3

Run npm explore webpack to customize the webpack package.json in a subshell (https://docs.npmjs.com/cli/explore)

Run npm docs webpack (https://docs.npmjs.com/cli/docs) to view the webpack docs

Run npm prune (https://docs.npmjs.com/cli/prune) to remove any unused packages

Run npm dedupe (https://docs.npmjs.com/cli/dedupe) to remove any duplicate packages

Run npm rebuild (https://docs.npmjs.com/cli/rebuild) to rebuild all the packages

Run npm shrinkwrap (https://docs.npmjs.com/cli/shrinkwrap) to lock down all the package files by version number

Check the shrinkwrap docs (http://npm.github.io/using-pkgs-docs/shrinkwrap/) for shrinkwrap troubleshooting

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

**Scaffolding**

<pre>
Grunt	                                   Webpack
grunt-contrib-copy	                   CopyWebpackPlugin
grunt-contrib-jshint	                   eslint-loader
grunt-contrib-sass	                   sass-loader
grunt-contrib-watch	                   Built-in; Use WatchIgnorePlugin to whitelist excluded files

karma-ng-html2js-preprocessor	           react-markdown
karma-ng-json2js-preprocessor	           JSONPTemplatePlugin(https://webpack.js.org/plugins/internal-plugins/#jsonptemplateplugin)

grunt-contrib-clean	                   CleanWebpackPlugin
grunt-useref	                           html-loader options (https://github.com/kangax/html-minifier#options-quick-reference)
grunt-remove-logging	                   Babel; set the comments config key to false
grunt.registerTask	                   apply-loader(https://github.com/mogelbrod/apply-loader)
grunt.file.copy                            CopyWebpackPlugin; Use transform (https://github.com/webpack-contrib/copy-webpack-plugin/blob/master/README.md#transform)
</pre>

**Cross-Browser Parity Testing**
1. Run in IE11, Chrome, and Firefox
1. Copy/Paste polyfills as an unminified script tag in index.html, then remove them one-by-one
1. Find the corresponding npm polyfills, then replace the copy/paste code with the minified generated code
1. Find the server.js source code and change its options to resolve server-side regressions
 

**Cross-Project Parity Testing**
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
* https://webpack.js.org/migrate/3
* https://developers.google.com/web/fundamentals/performance/webpack/use-long-term-caching
* https://github.com/webpack/webpack-dev-server/issues?utf8=%E2%9C%93&q=is%3Aissue+disablehostcheck+windows
* https://nodejs.org/en/blog/npm/npm-1-0-global-vs-local-installation/
* http://jdlm.info/articles/2016/03/06/lessons-building-node-app-docker.html
* https://blog.scottlogic.com/2018/02/13/npm-shrikwrap-merges-and-conflicts.html
* https://objectpartners.com/2016/08/02/how-to-not-be-afraid-of-transitive-dependencies-in-npm/
* http://jonnyreeves.co.uk/2016/npm-shrinkwrap-sucks/
* http://www.nikola-breznjak.com/blog/javascript/nodejs/npm-err-peerinvalid-the-package-node-inspector-does-not-satisfy-its-siblings-peerdependencies-requirements/
* https://futurestud.io/tutorials/how-to-fix-npm-package-does-not-satisfy-its-siblings-peerdependencies-requirements
* https://medium.com/@jacob.h.page/common-npm-mistakes-51bf8989079f
* http://www.grulic.org.ar/~mdione/glob/posts/installing-npm-on-debian-testing/
* https://blog.packagecloud.io/eng/2018/01/11/inspect-download-extract-npm-packages/
* https://docs.npmjs.com/cli/run-script
* https://npm.community/t/installing-upgrading-npm/251/2
* https://libraries.io/npm/npm/6.4.1
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
* https://medium.com/@jaketripp/cool-things-with-webpack-9a8019bdbd4a
* https://engineering.wingify.com/posts/migrating-towards-yarn-webpack/
* https://medium.com/@rajaraodv/webpack-the-confusing-parts-58712f8fcad9
* https://codeburst.io/maybe-dont-globally-install-that-node-js-package-f1ea20f94a00
* https://firstdoit.com/no-need-for-globals-using-npm-dependencies-in-npm-scripts-3dfb478908
* https://blog.angularindepth.com/this-will-make-you-more-efficient-at-debugging-wepback-unspecified-build-errors-6392850caed9
* https://dev.to/jhotterbeekx/getting-speed-back-my-webpack-debugging-journey-37a5
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
* https://www.reddit.com/r/javascript/comments/8s3fmy/if_webpack_40_is_about_zero_config_then_why_is/
* https://medium.com/@allycw/using-googles-closure-library-with-webpack-b944e2a4be3a
* https://www.colbyfayock.com/2018/08/reliable-and-maintainable-google-analytics-in-webpack/
* https://www.sitepoint.com/bundle-static-site-webpack/
* https://vijayt.com/post/scaffolding-react-web-app-webpack-2/
* http://ramkulkarni.com/blog/setting-up-webpack-babel-reactjs/

# Migration
* https://www.viget.com/articles/unpacking-the-mysteries-of-webpack-a-novices-journey/
* https://medium.com/webpack/how-to-cope-with-broken-modules-in-webpack-4c0427fb23a
* https://medium.com/@drgenejones/using-webpack-with-legacy-angular-spas-automating-imports-using-require-context-58e0e9cc6e9c#.sv9x4to9k
* https://github.com/DavidWells/react-angular-webpack
* https://medium.com/eventmobi/how-to-incrementally-switch-to-webpack-203a1b431f7a
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
* https://julienrenaux.fr/2015/03/30/introduction-to-webpack-with-practical-examples/

# Legacy Mapping
* https://www.npmjs.com/package/xslt-template-loader
* https://www.npmjs.com/package/svg-url-loader
* https://www.npmjs.com/package/freemarker-parser

# Middleware Security
* https://sdk.gooddata.com/gooddata-ui/docs/4.1.1/ht_configure_webpack_proxy.html
* https://superuser.com/questions/937013/override-localhost-ip-adress-in-windows-8-1/1367482#1367482
* https://medium.com/@anandshende1994/webpack-proxy-3ab759c022db
* https://medium.com/webpack/webpack-dev-server-middleware-security-issues-1489d950874a

## Environment Variables
* https://github.com/webpack/webpack/issues/7268
* https://stackoverflow.com/questions/49893669/how-can-i-access-runtime-environment-variables-from-a-webpack-compiled-script-th
* https://github.com/kentcdodds/webpack-config-utils

# Issues
* https://github.com/webpack/webpack/issues/3165
* https://github.com/webpack/webpack/issues/6617
* https://github.com/webpack/webpack/issues/1788
* https://github.com/webpack/webpack/issues/7615
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
* https://github.com/webpack/webpack/issues/1194
* https://github.com/YahooArchive/strip-loader/issues/24
* https://medium.com/@timurcatakli/how-i-fixed-webpack-4-loaderutils-parsequery-5a5e853619

# Mocking
* https://www.npmjs.com/package/mock-webpack-plugin
* https://cdn.polyfill.io/v3/polyfill.js

# HTML Email
https://blog.edmdesigner.com/css-inliner-tools-in-email/
https://www.smashingmagazine.com/2017/01/introduction-building-sending-html-email-for-web-developers/

# CSS
* https://material.io/develop/web/docs/getting-started/
* https://getbootstrap.com/docs/4.0/getting-started/webpack/
* https://blog.pagepro.co/2016/11/22/creating-amp-boilerplate-with-sass/
* https://github.com/JedWatson/react-select/issues/1324
* https://github.com/JedWatson/react-select/issues/176
* https://github.com/vuejs-templates/webpack/issues/604
* https://www.npmjs.com/package/web-resource-inliner
* https://github.com/webpack/webpack/tree/master/examples/loader
* https://stackoverflow.com/questions/42436728/webpack2-how-to-import-bootstrap-css-for-react-bootstrap-to-find-its-styles/42440360
* https://stackoverflow.com/questions/42500273/is-it-possible-to-use-the-css-loader-without-the-style-loader-in-webpack
* https://github.com/gajus/to-string-loader
* https://github.com/smithad15/css-to-string-loader
* https://css-tricks.com/the-debate-around-do-we-even-need-css-anymore/
* https://medium.com/@BMatt92656920/building-a-crud-application-with-react-webpack-bootstrap-2d80c45d5164
* https://medium.com/walkme-engineering/no-nonsense-webpack-project-bdfb79181737
* https://wanago.io/2018/07/16/webpack-4-course-part-two-webpack-4-course-part-two-loaders/
* https://github.com/webpack-contrib/style-loader/issues/255
* https://florianbrinkmann.com/en/4240/sass-webpack/
* https://github.com/webpack-contrib/css-loader/issues/585
* https://chriscourses.com/blog/purifycss-and-webpack
* https://github.com/webpack-contrib/file-loader/issues/272
* https://stackoverflow.com/questions/44204353/webpack-relative-css-url-with-file-loader-css-loader
* https://css-tricks.com/heres-the-thing-about-unused-css-tools/

# Concatenation
* https://code.luasoftware.com/tutorials/webpack/merge-multiple-javascript-into-single-file/

# Specs
* https://github.com/defunctzombie/package-browser-field-spec
* https://github.com/webpack/webpack/issues/520
* https://github.com/webpack/webpack/tree/master/schemas
* https://github.com/webpack/webpack-dev-server/issues/1713

# Benchmarking
* https://webpack.js.org/api/stats/
* https://github.com/webpack-contrib/webpack-bundle-analyzer
* https://webpack.js.org/configuration/performance/
* https://webpack.js.org/configuration/other-options/
* https://codeclimate.com/github/webpack/webpack/lib/Stats.js/source
* https://github.com/webpack/webpack/issues/5718
* https://www.smashingmagazine.com/2016/06/harness-machines-productive-task-runners/
* https://timber.io/blog/creating-a-real-world-cli-app-with-node/
* https://www.sitepoint.com/javascript-command-line-interface-cli-node-js/
* https://www.smashingmagazine.com/2017/03/interactive-command-line-application-node-js/
* https://opensource.com/article/18/7/node-js-interactive-cli
* https://www.smashingmagazine.com/2016/06/harness-machines-productive-task-runners/

# Malware
* https://news.ycombinator.com/item?id=16716264

# Plugin Dev
* https://github.com/evcohen/accessibility-webpack-plugin
* https://medium.com/@shellscape/webpacks-new-cli-hotness-d6a2063168a8

# Dev Server
* https://github.com/webpack/webpack-dev-server/blob/master/lib/Server.js#L696
* https://github.com/webpack/webpack-dev-server/blob/master/lib/options.json
* https://github.com/webpack/webpack-dev-server/blob/master/test/Validation.test.js
* https://github.com/webpack/webpack-dev-server/issues/887
* https://news.ycombinator.com/item?id=12406310
* https://medium.com/0xcc/visual-studio-code-silently-fixed-a-remote-code-execution-vulnerability-8189e85b486b
* https://medium.com/webpack/webpack-dev-server-middleware-security-issues-1489d950874a

# Aliasing
* https://medium.com/@justintulk/solve-module-import-aliasing-for-webpack-jest-and-vscode-74007ce4adc9
* http://xabikos.com/2015/10/03/Webpack-aliases-and-relative-paths/

# Localhost
* https://medium.com/webpack/webpack-dev-server-middleware-security-issues-1489d950874a

# Optimization
* https://webpack.js.org/configuration/optimization/
* https://webpack.js.org/configuration/devtool/
* https://webpack.js.org/guides/caching/
* https://webpack.js.org/concepts/mode/
* https://webpack.js.org/configuration/configuration-languages/
* https://webpack.js.org/configuration/watch/
* https://blog.benestudio.co/remove-console-log-statements-from-production-javascript-apps-7376adc89c7a
* https://github.com/webpack/webpack/issues/6586
* https://medium.com/@ottoki/adventures-with-webpack-manifest-and-commonschunkplugin-c89631fc87fb
* https://medium.com/@johntucker_48673/webpack-unraveling-commonschunkplugin-99b6a5fa5808
* https://developers.google.com/web/fundamentals/performance/webpack/use-long-term-caching

# Deployment
* https://devcenter.heroku.com/articles/nodejs-support
* https://devcenter.heroku.com/articles/node-best-practices
* https://www.dynatrace.com/news/blog/the-drastic-effects-of-omitting-node_env-in-your-express-js-applications/

# Transpilers
* https://www.sitepoint.com/javascript-modules-bundling-transpiling/
* https://appendto.com/2016/06/the-short-history-of-javascript-module-loaders/
* https://www.reddit.com/r/javascript/comments/2is81v/why_is_not_systemjs_dominating_the_field_of/

# Transpiler Plugins
* https://babeljs.io/docs/en/next/babel-helper-module-imports.html
* https://babeljs.io/docs/en/next/babel-plugin-syntax-export-default-from.html
* https://babeljs.io/docs/en/next/babel-plugin-syntax-export-namespace-from.html
* https://babeljs.io/docs/en/next/babel-plugin-transform-classes.html


# Internal Defaults
* https://babeljs.io/blog/2018/07/27/removing-babels-stage-presets
* https://webpack.js.org/configuration/node/
* https://github.com/webpack/webpack-dev-server/blob/master/test/Validation.test.js
* https://github.com/webpack/webpack/blob/master/lib/WebpackOptionsDefaulter.js
* https://github.com/webpack/webpack/blob/master/schemas/WebpackOptions.json

## Subsetting
* https://webpack.js.org/plugins/copy-webpack-plugin/
* https://www.npmjs.com/package/extract-loader
* https://webpack.js.org/configuration/module/#module-noparse
* https://webpack.js.org/plugins/define-plugin/
* https://webpack.js.org/plugins/npm-install-webpack-plugin/
* https://webpack.js.org/plugins/provide-plugin/
* https://webpack.js.org/loaders/json-loader/

## Feature Detection
* https://itnext.io/lazy-loading-polyfills-4b85c4951e73
* https://github.com/babel/babel/issues/7402
* https://www.smashingmagazine.com/2018/10/smart-bundling-legacy-code-browsers/
* https://css-tricks.com/polyfill-javascript-need/
* https://www.npmjs.com/package/dynamic-polyfill
* https://hackernoon.com/how-i-created-a-parallel-offline-extensible-browser-based-bundler-886db508cc31
* https://stackoverflow.com/questions/44764647/create-multiple-webpack-bundles-for-different-targets-and-have-browser-choose-ba
* https://stackoverflow.com/questions/42692827/how-to-load-webpack-bundles-async-but-execute-in-order

## Customization
* https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/webpack.html
* https://github.com/webpack-contrib/bundle-loader
* https://stackoverflow.com/questions/45645675/webpack-3-locates-mp4-file-but-video-is-not-playable
* https://github.com/mozilla/pdf.js/tree/master/examples/webpack
* https://www.npmjs.com/package/arraybuffer-loader
* https://www.npmjs.com/package/xml-loader
* https://www.npmjs.com/package/csv-loader
* https://webpack.js.org/guides/progressive-web-application/#adding-workbox
* https://webpack.js.org/guides/output-management/#the-manifest
* https://survivejs.com/webpack/extending/loaders/
* https://survivejs.com/webpack/optimizing/separating-manifest/
* https://adrien.harnay.me/2017-09-12-you-might-(not)-need-a-server-side-rendering-framework/
* https://codepen.io/reverland/post/exploring-webpack

## Snippets
<pre>
    // Copy .html and .css from src/ folder to default target in webpack
    plugins: [
        new copyWebpackPlugin([
                {
		    context: 'src/',
		    from: '*.css'
                },
		{
		    context: 'src/',
		    from: '*.html'
                }
            ])
        ],
</pre>