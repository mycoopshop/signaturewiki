CacheFactory would be the most portable and easiest to debug:

    function sharedCache($cacheFactory)
       {
       var sharedCache = $cacheFactory.get('sharedCache') ? $cacheFactory.get('sharedCache') : $cacheFactory('sharedCache');
    
       return sharedCache;
       }
    
    function bar(sharedCache)
       {
       var data = {
         firstName: 'John',
         lastName: 'Smith',
         pocket: 30
         };
    
       sharedCache.put('sharedCache', data);
       }
    
    bar.$inject = ['sharedCache', '$scope'];
    sharedCache.$inject = ['$cacheFactory'];
    
    angular.module('foo',[]);
    angular.module('foo').constant('sharedCache', sharedCache);
    angular.module('foo').run(bar);

Filters can read the data and output using ng-include and the templateCache. For example:
    
    function bop(name)
      {
      var data = baz.data.get('sharedCache');
      var tmpl = '';

      try
         {
         tmpl = tmpl.concat('<h1>',data.firstName, '</h1>');
         baz.tmpl.put(name, tmpl);
         }
      catch(e)
         {
         console.log(e);
         }
      }
    
    function baz($templateCache, sharedCache)
      {
      baz.tmpl = $templateCache;
      baz.data = sharedCache;
      return bop;
      }

    baz.$inject=['$templateCache', 'sharedCache'];
    angular.module('foo').filter('baz', baz);

With this markup:

    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.2.23/angular.min.js"></script>
    <div ng-app="foo">
      <div ng-include="'userContent' | baz"></div>
    </div>