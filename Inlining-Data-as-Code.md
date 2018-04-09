One way would be to serve the content as XML attributes, URL encoded strings, preformatted text with HTML encoded JSON, or data URIs, then transform it to HTML on the client. Here are a few sites which do this:

 * [Skechers](http://www.skechers.com/): XML

        <document 
         filename="" 
         height="" 
         width="" 
         title="SKECHERS" 
         linkType="" 
         linkUrl="" 
         imageMap="" 
         href=&quot;http://www.bobsfromskechers.com&quot; 
         alt=&quot;BOBS from Skechers&quot; 
         title=&quot;BOBS from Skechers&quot; 
        />


 * [Chrome Web Store](https://chrome.google.com/webstore/category/apps): JSON

        <script type="text/javascript" src="https://apis.google.com/js/plusone.js">{"lang": "en", "parsetags": "explicit"}</script>

 * [Bing News](http://www.bing.com/news): data URL

        <script type="text/javascript">
          //<![CDATA[
          (function()
            {
            var x;x=_ge('emb7');
            if(x)
              {
              x.src='data:image/jpeg;base64,/*...*/';
              } 
            }() )
 * [Protopage](http://www.protopage.com/): URL Encoded Strings

        unescape('Rolling%20Stone%20%3a%20Rock%20and%20Roll%20Daily')

 * [TiddlyWiki](http://tiddlywiki.com/) : HTML Entities + preformatted JSON

           <pre>
           {&quot;tiddlers&quot;: 
            {
            &quot;GettingStarted&quot;: 
              {
              &quot;title&quot;: &quot;GettingStarted&quot;,
              &quot;text&quot;: &quot;Welcome to TiddlyWiki,
              }
            }
           }
           </pre>

 * [Amazon](http://www.amazon.com/gp/aw/h.html): Lazy Loading

        amzn.copilot.jQuery=i;amzn.copilot.jQuery(document).ready(function(){d(b);f(c,function() {amzn.copilot.setup({serviceEndPoint:h.vipUrl,isContinuedSession:true})})})},f=function(i,h){var j=document.createElement("script");j.type="text/javascript";j.src=i;j.async=true;j.onload=h;a.appendChild(j)},d=function(h){var i=document.createElement("link");i.type="text/css";i.rel="stylesheet";i.href=h;a.appendChild(i)}})();
        amzn.copilot.checkCoPilotSession({jsUrl : 'http://z-ecx.images-amazon.com/images/G/01/browser-scripts/cs-copilot-customer-js/cs-copilot-customer-js-min-1875890922._V1_.js', cssUrl : 'http://z-ecx.images-amazon.com/images/G/01/browser-scripts/cs-copilot-customer-css/cs-copilot-customer-css-min-2367001420._V1_.css', vipUrl : 'https://copilot.amazon.com'

 * [XMLCalabash](http://xmlcalabash.com/extension/steps/library-1.0.xpl): Namespaced XML + Custom MIME type + Custom File extension

           <p:declare-step type="pxp:zip">
                <p:input port="source" sequence="true" primary="true"/>
                <p:input port="manifest"/>
                <p:output port="result"/>
                <p:option name="href" required="true" cx:type="xsd:anyURI"/>
                <p:option name="compression-method" cx:type="stored|deflated"/>
                <p:option name="compression-level" cx:type="smallest|fastest|default|huffman|none"/>
                <p:option name="command" select="'update'" cx:type="update|freshen|create|delete"/>
           </p:declare-step>

If you view source on any of the above, you see that scraping will simply return metadata and navigation.