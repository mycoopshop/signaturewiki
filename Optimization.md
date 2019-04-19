## Code
<pre>
       function init()
       {
            performance.mark("startTask1");
            doTask1(); // Some developer code
            performance.mark("endTask1");

            performance.mark("startTask2");
            doTask2(); // Some developer code
            performance.mark("endTask2");

            measurePerf();
       }

       function measurePerf()
       {
           var perfEntries = performance.getEntriesByType("mark");
           for (var i = 0; i < perfEntries.length; i++)
           {
                 if (window.console) console.log("Name: "        + perfEntries[i].name      +
                                                 " Entry Type: " + perfEntries[i].entryType +
                                                 " Start Time: " + perfEntries[i].startTime +
                                                 " Duration: "   + perfEntries[i].duration  + "\n");
           }
       }
</pre>

<pre>
       function loadResources()
       {
          var image1 = new Image();
          image1.onload = resourceTiming;
          image1.src = 'http://www.w3.org/Icons/w3c_main.png';
       }

       function resourceTiming()
       {
           var resourceList = window.performance.getEntriesByType("resource");
           for (i = 0; i < resourceList.length; i++)
           {
              if (resourceList[i].initiatorType == "img")
              {
                 alert("End to end resource fetch: "+ resourceList[i].responseEnd - resourceList[i].startTime);
              }
           }
       }
</pre>

## Specs

https://w3c.github.io/perf-timing-primer/

https://mimesniff.spec.whatwg.org

https://trends.builtwith.com/widgets/Battle-for-the-Net

https://trends.builtwith.com/widgets/Google-Font-API

https://www.sitepoint.com/non-blocking-async-defer/

https://chrome.google.com/webstore/detail/clacks-overhead-gnu-terry/lnndfmobdoobjfcalkmfojmanbeoegab?hl=en

## Web Workers

https://engineering.salesforce.com/optimizing-performance-with-web-workers-612b48621d8d

http://proceedings.esri.com/library/userconf/devsummit18/papers/dev-int-097.pdf

## Build Tooling Code Reuse

https://www.npmjs.com/package/microbundle

https://snugug.com/musings/unit-testing-gulp-tasks/

https://webpack.js.org/configuration/configuration-languages/#babel-and-jsx

https://gulpjs.org/recipes/using-external-config-file.html

https://da-14.com/blog/gulp-vs-grunt-vs-webpack-comparison-build-tools-task-runners

https://medium.com/@wisegain/gulp-vs-webpack-6d1dac0c505b

https://webdevstudios.com/2016/04/12/gulp-configuration-a-beginners-guide/

https://medium.com/webpack/unambiguous-webpack-config-with-typescript-8519def2cac7