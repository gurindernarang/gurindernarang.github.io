---
title: Handling CORS in ionic
layout: post
date: 2015-09-03 16:30:52 +0530
categories: Ionic CORS
tags: Ionic CORS
---
**CORS,** Cross-origin resource sharing **(CORS)** is a mechanism that allows restricted resources(e.g. fonts, JavaScript, etc.) on a web page to be requested from another domain outside the domain from which the resource originated.


Sometimes in **IONIC** if we are sending an AJAX request to server we get an error like this
{% highlight javascript %}
XMLHttpRequest cannot load http://api.ionic.com/endpoint.
No 'Access-Control-Allow-Origin' header is present on the requested resource.
Origin 'http://localhost:8100' is therefore not allowed access.
{% endhighlight %}
To handle such an error we have to enable CORS.

**How to handle CORS in ionic**

To enable CORS create another parameter inside ionic.project file as follow:
{% highlight javascript %}
{
  "name": "ProjectName",
  "app_id": "",
  "proxies": [
    {
      "path": "/api",
      "proxyUrl": "http://SERVER-URL/api"
    }
  ]
}
{% endhighlight %}
Now where you want to send request on an url send it as
{% highlight javascript %}
http://localhost:8100/api
{% endhighlight %}
It will proxy requests out to <b>http://SERVER_URL/api</b> on your behalf.

Source :- <span style="font-size: x-small;">http://blog.ionic.io/handling-cors-issues-in-ionic/</span>
