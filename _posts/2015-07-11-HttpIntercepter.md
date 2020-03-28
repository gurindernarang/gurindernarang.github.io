---
title: How to use http interceptor to handle http request and response in ionic
---
The <b>$http</b> service is a core Angular service that facilitates communication with the remote HTTP servers.<br>
In general we use it in our controller or service as follow :-
<blockquote>
<pre  style="font-family:arial;font-size:12px;border:1px dashed #CCCCCC;width:99%;height:auto;overflow:auto;background:#f0f0f0;;background-image:URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif);padding:0px;color:#000000;text-align:left;line-height:20px;"><code style="color:#000000;word-wrap:normal;"> // Simple GET request example :
 $http.get('/someUrl').
  success(function(data, status, headers, config) {
   // this callback will be called asynchronously
   // when the response is available
  }).
  error(function(data, status, headers, config) {
   // called asynchronously if an error occurs
   // or server returns response with an error status.
  });
</code>
</pre>
</blockquote>

The interceptors are service factories that are registered with the <b>$httpProvider</b> by adding them to the $httpProvider.interceptors array. The factory is called and injected with dependencies (if specified) and returns the interceptor.<br>

To use <b>$httpProvider</b> write the following code inside app.js as follow.

Inject <b>$httpProvider</b> provider inside .config :-
<blockquote>
<pre  style="font-family:arial;font-size:12px;border:1px dashed #CCCCCC;width:99%;height:auto;overflow:auto;background:#f0f0f0;;background-image:URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif);padding:0px;color:#000000;text-align:left;line-height:20px;"><code style="color:#000000;word-wrap:normal;"> .config(function ( $httpProvider){
 }
</code></pre>
</blockquote>
Inside this .config function add the following code :-
<blockquote>
<pre  style="font-family:arial;font-size:12px;border:1px dashed #CCCCCC;width:99%;height:auto;overflow:auto;background:#f0f0f0;;background-image:URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif);padding:0px;color:#000000;text-align:left;line-height:20px;"><code style="color:#000000;word-wrap:normal;">
   $httpProvider.interceptors.push(function($rootScope) {
     return {
       request: function(config) {
         return config
       },
       requestError: function(data, status, headers, config) {
         alert('Something went wrong.')
       },
       response: function(response) {
         return response
       },
       responseError:function(data, status, headers, config) {
         switch (status) {
           case 401:
             alert(data.message)
             break;
           case 500:
             alert('Internal Server Error')
             break;
           default:
             alert('Something went wrong.')
         }
         return data
       }
     }
   })
</code>
</pre>
</blockquote>
