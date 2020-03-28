---
title: Ionic slider in full screen
---
How to use ionic slider for intro and in fill screen in your ionic app.<br/><br/>
<b>Step 1:</b> Create ionic slider using the following code on your home screen
{% highlight javascript %}
<ion-view hide-nav-bar="true">
    <ion-slide-box on-slide-changed="slideChanged(index)">
        <ion-slide>
            <img class="fullscreen-image" src="image-name">
        </ion-slide>
        <ion-slide>
            <img class="fullscreen-image" src="image-name">
        </ion-slide>
        <ion-slide>
            <div class="arrow-position" ng-click="function-name()">
                <i class="ion-arrow-right-c"></i>
            </div>
            <img class="fullscreen-image" src="image-name">
        </ion-slide>
    </ion-slide-box>
</ion-view>
{% endhighlight %}
<b>Note:-</b> hide-nav-bar used to hide the navigation bar of your app.<br>
       function implemented on arrow must contain the code to move to the screen from where you want to start you app after intro.<br/><br/>

<b>Step 2:</b> Use the following css in using css or scss file to view your image on full screen.
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
<b>Note:-</b>Use this <b>fullscreen-image</b> class as mentioned above in the code.<br/><br/>
We can also change the color of ion-record using the following css.<br/>
{% highlight css %}
.ion-record {
  color:rgb(231,82,14);
  border: rgb(231,82,14);
}
{% endhighlight %}