---
title: Ionic cheatsheet
layout: post
date: 2015-09-18 12:15:48 +0530
categories: Ionic
tags: Ionic
---
 1. How to hide back button from a view.To hide ionic back button on desired page use following code inside ion-view tag.
{% highlight html %}
<ion-view hide-back-button="true">
</ion-view>
{% endhighlight %}

 2. How to navigation bar in a view
To hide navigation bar on a desired view use following code inside ion-view tag.
{% highlight html %}
<ion-view hide-nav-bar="true">
</ion-view>
{% endhighlight %}

 3. Scss to move title from top
{% highlight css %}
.bar {
  .title {
    margin-top: 4px;
  }
}
{% endhighlight %}

 4. Scss to use an image on ionic full screen<br>
{% highlight css %}
.fullscreen-image {
  max-width: 100%;
  max-height: 100%;
  bottom: 0;
  left: 0;
  right: 0;
  top: 0;
}
{% endhighlight %}