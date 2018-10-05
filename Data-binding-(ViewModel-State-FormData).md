## Angular

Use inline templates to separate views and filters instead of controllers:

    <script type="text/ng-template" id="/tpl.html">
      Content of the template.
    </script>

    <a ng-click="currentTpl='/tpl.html'" id="tpl-link">Load inlined template</a>
    <div id="tpl-content" ng-include src="currentTpl"></div>

Use $templateCache to perform loops, and $cacheFactory to pass data between filters rather than scope.

## XSLT

>The XSLT 2.0 specification defines tunnel parameters as having "the property that they are automatically passed on by the called template to any further templates that it calls, and so on recursively." When working on the big, complex stylesheets described above, if I could have identified the parameters passed to the original template as tunnel parameters, there would have been no need to explicitly pass them to templates that it called.

## HTML 

Use the :checked pseudo class to style checkboxes as presentational elements to emulate state, such as:

    .folder input[type='checkbox']:checked { display: block; }
    .folder input[type='checkbox'] { display: inline; }

Combine that with <label> elements as proxies to hide/show on demand, and nested `<blockquote>` elements as hierarchy.

    <div class="folder">
        <div>Blue
        <input type="checkbox" name="color"/>
        <blockquote>hi</blockquote>
        </div>
        <div>Red
        <input type="checkbox" name="color"/>
        <blockquote>bye</blockquote>
        </div>
    </div>

## React

Sometimes we think about components as being “special cases” of other components. For example, we might say that a WelcomeDialog is a special case of Dialog.

In React, this is also achieved by composition, where a more “specific” component renders a more “generic” one and configures it with props:

    function Dialog(props) {
      return (
        <FancyBorder color="blue">
          <h1 className="Dialog-title">
        
            {props.title}
          </h1>
      
          <p className="Dialog-message">
        
            {props.message}
          </p>
        </FancyBorder>
      );
    }

    function WelcomeDialog() {
      return (
        <Dialog
          title="Welcome"
          message="Thank you for visiting our spacecraft!" />

      );
    }

**References**

* [Angular 1.5 $Filter and $CacheFactory](https://www.youtube.com/watch?v=YMReoK4h1qA)

* [Understanding Angular's $templateCache](https://thinkster.io/templatecache-tutorial)

* [AngularJS: API: script](https://docs.angularjs.org/api/ng/directive/script)							

* https://stackoverflow.com/questions/26430757/invariant-violation-in-react-render-or-the-proper-way-to-iterate-and-return-in-r

* https://medium.com/@everdimension/how-to-handle-forms-with-just-react-ac066c48bd4f

* https://github.com/mozilla-services/react-jsonschema-form

* https://github.com/networknt/react-schema-form

* https://docs.microsoft.com/en-us/dotnet/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries