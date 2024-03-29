## Basic CORS for localhost development

1. Add your subdomain to the Origin Request header, e.g. foo.bar.com

1. Add the Access-Control-Allow-Origin Response header with your localhost value, e.g. localhost:9999

1. Add the Access-Control-Allow-Credentials Response header with a value of `true`

## Example

### Request Headers

    Host: example.com
    Origin: https://localhost:8081
    Referer: https://localhost:8081

### Response Headers

    Access-Control-Allow-Credentials: true
    Access-Control-Allow-Origin: localhost:8081
    Vary: Origin,Accept-Encoding,User-Agent

## References
1. http://blog.nelm.io/2011/11/cors-with-sencha-touch/
1. https://code-examples.net/en/q/12d42a4
1. https://www.moesif.com/blog/technical/cors/Authoritative-Guide-to-CORS-Cross-Origin-Resource-Sharing-for-REST-APIs/
1. https://help.crossbrowsertesting.com/faqs/testing/invalid-host-header-error/
1. https://medium.com/@BillFienberg/tunnels-and-proxies-and-headers-oh-my-5088e1ee11fa
1. https://www.elastic.co/guide/en/elasticsearch/reference/current/modules-http.html
1. https://developer.tizen.org/development/guides/web-application/w3chtml5supplementary-features/security/cross-origin-resource-sharing
1. https://w3c.github.io/webappsec-cors-for-developers/
1. https://news.ycombinator.com/item?id=12595628
1. https://github.com/nodejs/node/issues/14304
1. https://www.hostingadvice.com/how-to/nodejs__dirname/
1. https://host4asp.net/set-up-node-js-on-a-windows-server/
1. https://superuser.com/questions/395167/configuring-linux-to-use-windows-proxy
1. http://www.catonmat.net/http-proxy-in-nodejs/
1. https://atticuswhite.com/blog/apache-serving-nodejs/
1. https://adamtuttle.codes/add-node-to-existing-iis-server/
1. https://www.ocf.berkeley.edu/~xuanluo/sshproxywin.html
1. http://codebetter.com/matthewpodwysocki/2010/09/08/getting-started-with-node-js-on-windows/
1. http://knowledge.santanu.net/install-and-working-with-nodejs-on-windows-pc-and-openshift/
1. https://medium.com/@baphemot/understanding-cors-18ad6b478e2b
1. https://cdnjs.com/libraries/backbone.js/tutorials/cross-domain-sessions
1. https://expressjs.com/en/guide/behind-proxies.html
1. https://flaviocopes.com/express-cors/
1. https://www.express-gateway.io/
1. https://buer.haus/2017/03/08/airbnb-when-bypassing-json-encoding-xss-filter-waf-csp-and-auditor-turns-into-eight-vulnerabilities/