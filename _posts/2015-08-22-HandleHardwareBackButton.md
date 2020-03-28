---
title: Handle hardware back button in Ionic.
---
Create a service in ionic with the following javascript code:<br>

<pre  style="font-family:arial;font-size:12px;border:1px dashed #CCCCCC;width:99%;height:auto;overflow:auto;background:#f0f0f0;;background-image:URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif);padding:0px;color:#000000;text-align:left;line-height:20px;"><code style="color:#000000;word-wrap:normal;">  this.deregister = undefined;
    this.disable = function () {
      this.deregister = $ionicPlatform.registerBackButtonAction(function (e) {
        e.preventDefault();
        return false;
      }, 101);

    }
    this.enable = function () {
      if (this.deregister !== undefined) {
        this.deregister();
        this.deregister = undefined;
      }
    }
</code></pre>

Inside app.js inside .run function write a function which gets call when we click on hardware back button.<br>

<pre  style="font-family:arial;font-size:12px;border:1px dashed #CCCCCC;width:99%;height:auto;overflow:auto;background:#f0f0f0;;background-image:URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif);padding:0px;color:#000000;text-align:left;line-height:20px;"><code style="color:#000000;word-wrap:normal;">
1:  $ionicPlatform.onHardwareBackButton(function () {
2:        console.log("Event " + JSON.stringify());
3:        if (true) {
5:          $ionicPopup.confirm({
6:            template: 'template for pop up'
7:          }).then(function (res) {
8:            if (res) {
9:              navigator.app.exitApp();
10:            }
11:          })
12:        }
13:      });
</code></pre>

Now inside your controller where you want to disable the back button, inject the service and call its disable method as follow.<br>

<pre  style="font-family:arial;font-size:12px;border:1px dashed #CCCCCC;width:99%;height:auto;overflow:auto;background:#f0f0f0;;background-image:URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif);padding:0px;color:#000000;text-align:left;line-height:20px;"><code style="color:#000000;word-wrap:normal;">
1:   HardwareBackButtonManager.disable();
</code></pre>