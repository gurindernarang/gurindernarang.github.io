---
title: Tabs in Ionic
---


Open a page in same tab. In app.js create a new state having same tab name as mention above in the code

{% highlight javascript linenos %}

.state('tab.demo', {
    url: '/demo',
    views: {
    'tab-demo': {
        templateUrl: 'templates/dummy-main.html',
        controller: 'DummyCtrl'
        }
    }
})
.state('tab.demo', {
    url: '/demo',
    views: {
    'tab-demo': {
        templateUrl: 'templates/dummy.html',
        controller: 'DummyCtrl'
        }
    }
});

{% endhighlight %}

In tabs.html ion-tab has a ion-nav-view element inside of it. The ion-nav-view is where our child states
(the views of our app) will be inserted and If we call ionic view content from tabs.html it acts as main
tab view and if we call it from anywhere else then it open in the same tab with a back button at the top.
We can have number of pages under same tab in ionic defined in app.js.