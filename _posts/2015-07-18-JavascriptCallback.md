---
title: Callback in javascript
---
<div dir="ltr" style="text-align: left;" trbidi="on">
<div dir="ltr" style="text-align: left;" trbidi="on">
A callback function  is a function that is passed to another function as parameter and the callback function is called (or executed) inside another function.<br />
&nbsp;e.g :-<br />
<pre style="background-image: URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif); background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> var func1 = function(args ,callback){
 }   </code>&nbsp;</pre>
When we pass a callback function as an argument to another function, we
 are only passing the function definition. We are not executing the
function in the parameter. In other words, we aren’t passing the
function with the trailing pair of executing parenthesis () like we do
when we are executing a function.<br />
<br />
How to make sure that Callback is a function before executing it??<br />
It is always wise to check that the callback function passed in the
parameter is indeed a function before calling it. Also, it is good
practice to make the callback function optional.<br />
Let's refactor the above code as follow :-<br />
<pre style="background-image: URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif); background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> var func1 = function(args ,callback){
 .......
 if (typeof callback == "function") {
       callback();
     } else {
       console.log("No callback defined");
     }
 }
</code></pre>
<br />
How to call a callback function??<br />
Now we have to use this callback function after executing <b>func1</b> function. So define callback inside <b>func1</b>. Normally we call a function using just its name and pass arguments inside it but in this case we define function as second argument.<br />
e.g :-
<br />
<pre style="background-image: URL(http://2.bp.blogspot.com/_z5ltvMQPaa8/SjJXr_U2YBI/AAAAAAAAAAM/46OqEP32CJ8/s320/codebg.gif); background: #f0f0f0; border: 1px dashed #CCCCCC; color: black; font-family: arial; font-size: 12px; height: auto; line-height: 20px; overflow: auto; padding: 0px; text-align: left; width: 99%;"><code style="color: black; word-wrap: normal;"> func1(args ,function(){
  console.log("Call back will executed after fun1 returns the result");
 });&nbsp; </code></pre>
</div>
<br />
Source :- <span style="font-size: x-small;"><a href="http://javascriptissexy.com/understand-javascript-callback-functions-and-use-them/#" target="_blank">http://javascriptissexy.com/understand-javascript-callback-functions-and-use-them/#</a></span></div>
