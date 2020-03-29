---
title: How to run angular application
layout: post
date: 2015-09-28 12:30:13 +0530
categories: Angular
tags: Angular
---
To run an angular application make sure that you have bower, gulp and npm installed globally.

After creating or downloading angular project inside that folder run following commands set of commands:
{% highlight javascript %}
bower install
{% endhighlight %}
The above command will install all the bower dependencies, then run
{% highlight javascript %}
npm install
{% endhighlight %}
**npm install** command will install all the node libraries
{% highlight javascript %}
gulp serve
{% endhighlight %}
Read gulp.js and run the local server. To generate files for deployment use the following command
{% highlight javascript %}
gulp build
{% endhighlight %}
