## Slow Loop [Back](./../goog.md)
###Problem
```js
/* from Google Closure 
 * from array.js, Line 63
 * 每次循環都要查找屬性值而增加開銷
*/
for (var i = fromIndex; i < arr.length; i++) {
```

###Solution
```js
/*
 * Use a variable to store the value of attributes
*/
for (var i = fromIndex, len = arr.length; i < len; i++) {	
```

<a href="#" style="left:200px;"><img src="./../../../../../pic/gotop.png"></a>
=====
<a href="http://aleen42.github.io/" target="_blank" ><img src="./../../../../../pic/tail.gif"></a>