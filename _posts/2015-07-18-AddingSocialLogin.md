---
title: Adding social login in ionic using Firebase
---
<div dir="ltr" style="text-align: left;" trbidi="on">
Steps to add social login button for github in ionic<br />
<ol style="text-align: left;">
<li>Create a new application in github <a href="https://github.com/settings/applications/new" target="_blank">from here</a>.</li>
<li>Once the GitHub app is created, we’ll take a client ID and a client
secret and paste them into the GitHub authentication section in our
Firebase app dashboard.</li>
<li>Create a new app in ionic</li>
<pre style="background-image: URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif); background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> $ ionic start myApp blank
 $ cd myApp
 $ ionic plugin add cordova-plugin-inappbrowser
 $ ionic add angularfire
</code></pre>
<li>&nbsp;Add the following files in ionic</li>
<pre style="background-image: URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif); background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> &lt;script src="lib/firebase/firebase.js"&gt;&lt;/script&gt;
 &lt;script src="lib/angularfire/dist/angularfire.min.js"&gt;&lt;/script&gt;
</code></pre>
<li>Inject Firebase as a dependency of your app as follow in app.js</li>
<pre style="background-image: URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif); background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> angular.module('starter', ['ionic', 'firebase'])
</code></pre>
<li>Inside contoller add the following function</li>
<pre style="background-image: URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif); background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;">  $scope.loginGithub = function(authMethod) {
     var ref = new Firebase("https://gurinder.firebaseio.com");
     ref.authWithOAuthPopup("github", function(error, authDataGithub) {
       if (error) {
         console.log("Login Failed!", error);
       } else {
         $scope.authDataGithub = authDataGithub;
         console.log("Authenticated successfully with payload:", authDataGithub);
       }
     });
   };
</code></pre>
<li>Call this function on button click inside HTML file</li>
<pre style="background-image: URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif); background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> &lt;ion-pane ng-controller="AppCtrl"&gt;
  &lt;ion-content&gt;
   &lt;button class="button button-royal icon ion-social-github" ng-click="</code><code style="color: black; word-wrap: normal;"><code style="color: black; word-wrap: normal;">loginGithub</code>()"&gt;&lt;/button&gt;
  &lt;/ion-content&gt;
 &lt;/ion-pane&gt;
</code></pre>
</ol>
We need just few changes to Login using other social sites like facebook, twiiter etc. Refer to&nbsp;<a href="http://blog.ionic.io/adding-social-login-with-firebase/" target="_blank">this link</a> to do that. &nbsp;
</div>
