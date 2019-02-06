## Webhooks

WebHooks are an HTTP POST callback request sent to URL of a user's choice in response to some event occurring. For example:

Event Subscription via URL => Timestamp Change Event => HTTP POST callback => Synchronization 

## WebSub

Publish the feed to superfeedr

The first time you fetch the feed, look for `<link>` element with `rel=hub` in it:

    <feed xmlns="http://www.w3.org/2005/Atom">
      <title>Superfeedr Blog : Real-time cloudy thoughts from a super-hero</title>
      <link href="https://superfeedr-blog-feed.herokuapp.com/" rel="self" type="application/atom+xml"/>
      <link href="http://blog.superfeedr.com/" rel="alternate" type="text/html"/>
      <link rel="hub" href="http://pubsubhubbub.superfeedr.com/" />
      <updated>2015-02-03T13:08:02+01:00</updated>
      <id>http://blog.superfeedr.com/</id>
    ...
    </feed>

The most important line is:

    <link rel="hub" href="http://pubsubhubbub.superfeedr.com/" />

It tells us that this feed is available in real-time at this community hub.

The second most important line is:

    <link href="https://superfeedr-blog-feed.herokuapp.com/" rel="self" type="application/atom+xml"/>

It tells us the canonical URL for this feed. It's the actual feed URL that we should use for subscriptions. Most of the time it will be this URL that you might have fetched, but sometimes, it may differ and when that happens, you need to use the self URL.

## Subscription

The subscription request is a POST HTTP request. You can issue it using a command line tool like curl or any other type of HTTP library and client. The subscription request is sent to the hub URL (see discovery above).

## References
1. https://blog.superfeedr.com/howto-pubsubhubbub/
1. https://nordicapis.com/webhooks-vs-websub-which-one-is-better-to-stream-your-events-in-real-time/
1. https://www.programmableweb.com/news/what-are-webhooks-and-how-do-they-enable-real-time-web/2012/01/30
1. https://www.programmableweb.com/news/what-pubsubhubbub-push-styled-api-and-how-does-it-work/analysis/2017/04/03
1. https://stackoverflow.com/questions/36825042/consuming-rss-feed-with-aws-lambda-and-api-gateway
1. https://developers.google.com/youtube/v3/guides/push_notifications
1. https://github.com/pubsubhubbub/PubSubHubbub/wiki/RSS-Feeds

## Proxies
* https://www.cisco.com/c/en/us/td/docs/security/web_security/connector/connector2972/PACAP.html
* https://auth0.com/blog/heads-up-https-is-not-enough-when-using-wpad/
* https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file
* https://holtstrom.com/michael/blog/post/225/Apache-2.2-Proxy.html
* http://httpd.apache.org/docs/current/rewrite/proxy.html
* https://dzone.com/articles/solving-the-options-performance-issue-with-single
* https://arpitonline.com/2017/02/09/serving-multiple-reactjs-apps-with-express/
* https://medium.com/@whale_eat_squid/why-http-2-isnt-the-answer-35ba28ad8dc3
* https://wikitech.wikimedia.org/wiki/Performance/Proxy_browsers
* https://stackoverflow.com/questions/50321034/how-do-enable-root-proxying-in-webpack-dev-server
* https://github.com/chimurai/http-proxy-middleware#context-matching
* https://gorillalogic.com/blog/webpack-and-cors/
* https://daniel.haxx.se/blog/2016/11/26/https-proxy-with-curl/