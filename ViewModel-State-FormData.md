Use inline templates to separate views and filters instead of controllers:

    <script type="text/ng-template" id="/tpl.html">
      Content of the template.
    </script>

    <a ng-click="currentTpl='/tpl.html'" id="tpl-link">Load inlined template</a>
    <div id="tpl-content" ng-include src="currentTpl"></div>

Use $templateCache to perform loops, and $cacheFactory to pass data between filters rather than scope.

**References**

* [Angular 1.5 $Filter and $CacheFactory](https://www.youtube.com/watch?v=YMReoK4h1qA)

* [Understanding Angular's $templateCache](https://thinkster.io/templatecache-tutorial)

* [AngularJS: API: script](https://docs.angularjs.org/api/ng/directive/script)							

* https://stackoverflow.com/questions/26430757/invariant-violation-in-react-render-or-the-proper-way-to-iterate-and-return-in-r

* https://medium.com/@everdimension/how-to-handle-forms-with-just-react-ac066c48bd4f