## Indexing Metadata

Use a JSON structure with a key for each thing you have and each thing you need to match via a string method. For example:
* URL path
* Title
* keywords

<pre>
var searchengine = 
{
[
  {
    "path": "api",
    "titleWords": "API Reference",
    "keywords": "$animate $aria $ariaprovider $compile $cookie $cookies $cookiestore $http $httpbackend $interval $location $log $resource $route $routeparams $routeprovider $sanitize $swipe $timeout access accessed accessibility accidental alert alert-info an and angular angularjs animation animations api apis application applying are aria as attached attributes available aware be become before behavior being both browser browsers build by callbacks can class clean code collection collisions common communicate complex components configuring contain contains convenient cookie cookies copy core css css-based currency current currently dangerous data date default define defined definition-table dependency details developing di directive directives disabilities display do docs documentation dom dump element emulate enable equals etc events examples experience expressions extend factories features file filter filters follow following for function functions global guide handle hashbang helper hooks html html5 improve in include included index inject into is it javascript js js-based keyframe level links linky low lowercase manage manageable management manipulate manner materials methods mobile mock mocks module modules more name names naming ng ng-bind nganimate ngaria ngclick ngcookies nginclude ngmock ngrepeat ngresource ngroute ngsanitize ngtouch ngview not object objects of once operations or organized overview page pages parse partials please posting prefix prefixes present prevent private provide provided providers public pushstate querying querystring quick reference referencing register registered rendered rest restful route routes routing runner securely serialization service services set simple some spaced store string structure supports synchronous template templates test testing tests that the these this to transform transitions trigger triggered turn unit up uppercase url urls use used useful users using values various version via way welcome when which will with within work would wrapper you your",
    "members": ""
  }
]
};
</pre>


## References
https://wiki.apache.org/solr/UnicodeCollation

https://opensourceconnections.com/blog/2017/02/20/solr-utf8/

https://lucene.apache.org/solr/guide/6_6/tokenizers.html

https://lucene.apache.org/solr/guide/6_6/filter-descriptions.html

https://home.apache.org/~hossman/apachecon2008us/ootb/apache-solr-out-of-the-box.pdf

http://assets.en.oreilly.com/1/event/61/Solr%20Application%20Development%20Tutorial%20Presentation.pdf

https://archive.apachecon.com/eu2007/materials/solr-talk.pdf

http://archive.apachecon.com/eu2012/presentations/06-Tuesday/PR-Lucene/aceu-2012-solr-4-the-NoSQL-database.pdf