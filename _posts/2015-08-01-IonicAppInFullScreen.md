---
title: Open ionic app in full screen
---
To hide the status bar in an Ionic application, we use the Cordova status bar plugin.Install the status bar plugin from the given link.<br>
[Status bar](http://ngcordova.com/docs/plugins/statusbar/)<br>
Inside app.js write the following code inside .run method<br>
{% highlight javascript linenos %}
app.run(function($cordovaStatusbar){
  $ionicPlatform.ready(function () {
		    $cordovaStatusbar.hide();
	    })
	})
{% endhighlight %}