Use the client-side service discovery pattern: 

[![service discovery pattern][1]][1]
>The network location of a service instance is registered with the service registry when it starts up. It is removed from the service registry when the instance terminates. The service instance’s registration is typically refreshed periodically using a heartbeat mechanism.

>Netflix OSS provides a great example of the client‑side discovery pattern. Netflix Eureka is a service registry. It provides a REST API for managing service‑instance registration and for querying available instances. Netflix Ribbon is an IPC client that works with Eureka to load balance requests across the available service instances. We will discuss Eureka in more depth later in this article.

>The client‑side discovery pattern has a variety of benefits and drawbacks. This pattern is relatively straightforward and, except for the service registry, there are no other moving parts. Also, since the client knows about the available services instances, it can make intelligent, application‑specific load‑balancing decisions such as using hashing consistently. One significant drawback of this pattern is that it couples the client with the service registry. You must implement client‑side service discovery logic for each programming language and framework used by your service clients.


  [1]: https://i.stack.imgur.com/4zylX.png

Once you discover the service, you can discover the API if it uses a well-known standard such as GraphQL:

>GraphQL is introspective. This means you can query a GraphQL schema for details about itself.

>Query __schema to list all types defined in the schema and get details about each:

    query LearnAboutSchema {
      __schema {
        types {
          name
          kind
        }
        queryType {
          fields {
            name
            description
          }
        }
      }
    }


or an auto-discovery method on a URL such as Wordpress:

>To utilize the auto-discovery functionality, call WPAPI.discover() with a URL within a WordPress REST API-enabled site:

>var apiPromise = WPAPI.discover( 'http://my-site.com' );

or a discovery metadata such as MediaWiki:

>Since r75621, we have RSD discovery for the endpoint: look for the link rel="EditURI" in the HTML source of any page and extract the api.php URL; the actual link contains additional info.

or a HTTP header response, as per RFC 7231:

>How about serving the Swagger JSON in an HTTP response body, in response to an OPTIONS request for the URL / ?

>The OPTIONS method requests information about the communication options available for the target resource, at either the origin server or an intervening intermediary.  This method allows a client to determine the options and/or requirements associated with a resource, or the capabilities of a server, without implying a resource action.

**References**

* [Service Discovery in a Microservices Architecture - NGINX](https://www.nginx.com/blog/service-discovery-in-a-microservices-architecture/)

* [Choosing A Service Discovery System – WorkMarket Engineering](https://workmarket.tech/choosing-a-service-discovery-system-1979ee55c728)

* [Discovering the GraphQL API](https://developer.github.com/v4/guides/intro-to-graphql/#discovering-the-graphql-api)

* [Using the REST API: Discovery](https://developer.wordpress.org/rest-api/using-the-rest-api/discovery/)

* [node-wpapi Github repo: auto-discovery](https://github.com/WP-API/node-wpapi#auto-discovery)

* [MediaWiki API Help](https://www.mediawiki.org/w/api.php)

* [API:Main page - MediaWiki](https://www.mediawiki.org/wiki/API:Main_page)