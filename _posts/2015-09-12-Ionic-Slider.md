---
title: Ionic slider in full screen
layout: post
date: 2015-09-12 10:49:23 +0530
categories: Ionic
tags: Ionic
---
How to use ionic slider to give intro of your application in full screen in your ionic app.<br/><br/>
**Step 1:** Create ionic slider using the following code on your home screen

{% highlight javascript %}
<ion-view hide-nav-bar="true">
    <ion-slide-box on-slide-changed="slideChanged(index)">
        <ion-slide>
            <img class="fullscreen-image" src="image-name" alt=""/>
        </ion-slide>
        <ion-slide>
            <img class="fullscreen-image" src="image-name" alt=""/>
        </ion-slide>
        <ion-slide>
            <div class="arrow-position" ng-click="function-name()">
                <i class="ion-arrow-right-c"></i>
            </div>
            <img class="fullscreen-image" src="image-name" alt=""/>
        </ion-slide>
    </ion-slide-box>
</ion-view>
{% endhighlight %}

**Note:** hide-nav-bar used to hide the navigation bar from your application.
        Function implemented on arrow must contain the code to move to the screen from where you want to start your application after intro.

**Step 2:** Use the following css in css or scss file to view the images in full screen
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
**Note:** Use this **fullscreen-image** class as mentioned above in the code.

We can also change the color of ion-record using the following css.
{% highlight css %}
.ion-record {
    color:rgb(231,82,14);
    border: rgb(231,82,14);
}
{% endhighlight %}