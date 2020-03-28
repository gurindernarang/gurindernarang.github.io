---
title: Handling CORS in ionic
---
<b>CORS</b><br>
 Cross-origin resource sharing (CORS) is a mechanism that allows restricted resources (e.g. fonts, JavaScript, etc.) on a web page to be requested from another domain outside the domain from which the resource originated
 <br><br>Sometimes in <b>IONIC</b> if we are sending an AJAX request to server we get an error like this
 {% highlight javascript linenos %}
 XMLHttpRequest cannot load http://api.ionic.com/endpoint.
 No 'Access-Control-Allow-Origin' header is present on the requested resource.
 Origin 'http://localhost:8100' is therefore not allowed access.
 {% endhighlight %}
 To handle such an error we have to enable CORS.<br><br>
 <b>How to handle CORS in ionic</b><br>
 To enable CORS create another parameter inside ionic.project file as follow
 {% highlight javascript linenos %}
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
 Now where you want to send request on an url send it as<br>
 {% highlight javascript linenos %}
 http://localhost:8100/api
 {% endhighlight %}
 it will proxy requests out to <b>http://SERVER_URL/api</b> on your behalf.
 <br />
 Source :- <span style="font-size: x-small;">http://blog.ionic.io/handling-cors-issues-in-ionic/</span>
