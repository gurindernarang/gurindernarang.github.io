---
title: How to provide loader on each <b>$httpProvider</b> request
---
To implement this first we have to know about angular's <b>$broadcast</b>.<br>
Its syntax is as below :
  {% highlight javascript %}
    $broadcast(name, args);
  {% endhighlight %}
<b>$broadcast</b> dispatches an event name downwards to all child scopes (and their children) notifying the registered $rootScope.Scope listeners.<br>
The event life cycle starts at the scope on which $broadcast was called. All listeners listening for name event on this scope get notified. Afterwards, the event propagates to all direct and indirect scopes of the current scope and calls all registered listeners along the way. The event cannot be canceled.
<br>
<h1>How to use in ionic</h1>
Inside app.js use the following code

{% highlight javascript %}
app.config(function($httpProvider) {
  $httpProvider.interceptors.push(function($rootScope) {
    return {
      request: function(config) {
        $rootScope.$broadcast('loading:show')
        return config
      },
      response: function(response) {
        $rootScope.$broadcast('loading:hide')
        return response
      }
    }
  })
})
app.run(function($rootScope, $ionicLoading) {
  $rootScope.$on('loading:show', function() {
    $ionicLoading.show({template: 'foo'})
  })

  $rootScope.$on('loading:hide', function() {
    $ionicLoading.hide()
  })
})
{% endhighlight %}