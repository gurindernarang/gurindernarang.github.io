---
title: Ionic useful commands
---
<ul>
    <li>
     How to hide back button in a view<br>
       To hide ionic back button on desired page use following code inside ion-view tag.
        {% highlight html %}
        <ion-view hide-back-button="true">
        </ion-view>
        {% endhighlight %}
    </li><br>
    <li>
     How to navigation bar in a view<br>
       To hide navigation bar on a desired view use following code inside ion-view tag.
         {% highlight html %}
         <ion-view hide-nav-bar="true">
         </ion-view>
         {% endhighlight %}
    </li>
    <li>
         Scss to move title from top<br>
             {% highlight css %}
             .bar
             {
             .title
             {
             margin-top: 4px;
             }
             }
             {% endhighlight %}
    </li>
    <li>
             Scss to use an image on ionic full screen<br>
                 {% highlight css %}
                 .fullscreen-image
                 {
                 max-width: 100%;
                 max-height: 100%;
                 bottom: 0;
                 left: 0;
                 right: 0;
                 top: 0;
                 }
                 {% endhighlight %}
    </li>

</ul>
