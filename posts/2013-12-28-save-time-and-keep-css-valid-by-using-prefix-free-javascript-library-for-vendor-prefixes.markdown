---
layout: post
title: Save time and keep your CSS valid by using -prefix-free javascript library
  for vendor prefixes
date: 2013-12-28 09:38:57.000000000 +05:30
---
<img class="alignnone size-full wp-image-112" title="vendor-prefixes" src="/content/images/2011/Oct/vendor-prefixes.gif" alt="" width="561" height="170" />

When we write CSS many time we use <a href="http://peter.sh/experiments/vendor-prefixed-css-property-overview/" target="_blank">browser specific vendor prefixes</a> to use newer CSS 3 properties in our project and it makes the code bigger and hard to maintain because every time we need to change the value of propert we need to change for all vendor-prefixes for all browser.
<pre lang="css" line="1" escaped="true">.example {
background: red;
color: #fff
height: 200px;
margin: 30px;
padding: 10px;
width: 300px;&lt;/code&gt;

box-shadow: 0.2em 0.4em 0.8em -0.2em black;
-moz-box-shadow: 0.2em 0.4em 0.8em -0.2em black;
-webkit-box-shadow: 0.2em 0.4em 0.8em -0.2em black;

transform-origin: 0% 0%;
-moz-transform-origin: 0% 0%;
-ms-transform-origin: 0% 0%;
-o-transform-origin: 0% 0%;
-webkit-transform-origin: 0% 0%;

transform: scale(0.8) rotate(10deg);
-moz-transform: scale(0.8) rotate(10deg);
-ms-transform: scale(0.8) rotate(10deg);
-o-transform: scale(0.8) rotate(10deg);
-webkit-transform: scale(0.8) rotate(10deg);

border-radius: 15px;
-moz-border-radius: 15px;
-webkit-border-radius: 15px;
}</pre>
It's hard to remember all vendor prefixes and even if you remember it takes time to write vendor prefixe for each browser so I was using an online tool <a href="http://cssprefixer.appspot.com/" target="_blank">CSSPrefixer</a>. There is one similar tool called <a href="http://prefixr.com/" target="_blank">Prefixfer</a> too.

<a href="http://cssprefixer.appspot.com/"><img class="alignnone size-full wp-image-113" title="cssprefixer" src="/content/images/2011/Oct/cssprefixer.gif" alt="" width="561" height="240" /></a>

It adds vendor prifixes automatically if we give W3C standards properties and value for needed browser specific property. for example <a href="http://cssprefixer.appspot.com/" target="_blank">CSSPrefixer</a> convert this code which has 4 properties
<pre lang="css" line="1" escaped="true">.example {
transform: scale(0.8) rotate(10deg);
transform-origin: 0% 0%;
box-shadow: .2em .4em .8em -.2em black;
border-radius: 15px; width:300px}</pre>
into this
<pre lang="css" line="1" escaped="true">.example {
    -webkit-transform: scale(0.8) rotate(10deg);
    -moz-transform: scale(0.8) rotate(10deg);
    -o-transform: scale(0.8) rotate(10deg);
    -ms-transform: scale(0.8) rotate(10deg);
    transform: scale(0.8) rotate(10deg);

    -webkit-transform-origin: 0% 0%;
    -moz-transform-origin: 0% 0%;
    -o-transform-origin: 0% 0%;
    -ms-transform-origin: 0% 0%;
    transform-origin: 0% 0%;

    -webkit-box-shadow: 0.2em 0.4em 0.8em -0.2em black;
    -moz-box-shadow: 0.2em 0.4em 0.8em -0.2em black;
    box-shadow: 0.2em 0.4em 0.8em -0.2em black;

    -webkit-border-radius: 15px;
    -moz-border-radius: 15px;
    border-radius: 15px;
     }</pre>
But This above code has 12 vendor specific properties, 14 properties extra. it makes the css file longer and each time when we want to change any value of same property we will have to change in each vendor prefix which increase the CSS debugging time when do quick changes on ftp or testing something locally.

<a href="http://lea.verou.me/">Lea Verou</a>  release a good solution called -<a href="http://leaverou.github.com/prefixfree/" target="_blank">prefix-free</a>. It's a lightweight (5KB) JavaScript library which add the vendor prefixes on runtime whenever required on particular browser. So we don't need to keep vendor prefixes in our css file.

<a href="http://leaverou.github.com/prefixfree/"><img class="alignnone size-full wp-image-114" title="prefixfree" src="/content/images/2011/Oct/prefixfree.jpg" alt="" width="561" height="170" /></a>

How to use this ? Just include prefixfree.js anywhere in your page. That’s it, you’re done!

For example This is a code in our css. No need to write vendor prefixes.
<pre lang="css" line="1" escaped="true">.example {
transform: scale(0.8) rotate(10deg);
transform-origin: 0% 0%;
box-shadow: .2em .4em .8em -.2em black;
border-radius: 15px; width:300px}</pre>
now <a href="https://raw.github.com/LeaVerou/prefixfree/master/prefixfree.min.js" target="_blank">download -prefix-free</a>and keep inside..<script type="text/javascript" src="js/prefixfree.min.js"></script>

Now refresh your page and check in browser all properties will work as usual because prefixfree added only needed properties to the page.

For example it will add to Chorme and Safari. You can check added properties by selecting element using Firebug or Chrome Developer toools
<pre lang="css" line="1" escaped="true">-webkit-transform: scale(0.8) rotate(10deg);
-webkit-transform-origin: 0% 0%;
-webkit-transform-origin-x: 0%;
-webkit-transform-origin-y: 0%;</pre>
<strong>I made an Example of show how it works</strong> <a href="CSSPrefixer" target="_blank">http://jsbin.com/ipovir/4/edit</a>

Advantage of using this JavaScript library are
<ul>
	<li>It will keep our css tidy</li>
	<li>We don't need to worry about which browser's vendor prefixes we added or for which not. It add automatically</li>
	<li>Making changes in CSS3 properties will be easier</li>
	<li>It will keep our CSS valid</li>
</ul>
There are some disadvantage too because styling will be dependent on JavaScript and one extra http request but in today's HTML5 CSS3 World we are already using the libraries like HTML5 Shim, jQUery, MooTools, Modernizer, CSS3 Pie etc. Read <a href="http://lea.verou.me/">Lea Verou's</a> <a href="http://css-tricks.com/14792-five-questions-with-lea-verou/#lea-question-2">Interview's 2nd question and her answers about pros and cons of Prefix-free on css-tricks.com</a>

prefixfree has some more features and limitations. Check its official page for more info <a href="http://leaverou.github.com/prefixfree/" target="_blank">http://leaverou.github.com/prefixfree/</a>
<h2><a href="https://raw.github.com/LeaVerou/prefixfree/master/prefixfree.min.js" target="_blank">Download -prefix-free</a></h2>
Now it's also available as a jQuery Plugin <a href="http://leaverou.github.com/prefixfree/#plugins">http://leaverou.github.com/prefixfree/#plugins</a>

Please share your thoughts about it in comment.
