---
layout: post
title: 'Firebug tip: How to switch :hover and :active state of link to see live changes?'
date: 2010-09-26 09:38:57.000000000 +05:30
---


<img src="{{ site.url }}/images/firebug-tip.gif" alt="Firebug: A useful tool for web development">

Here I'm sharing a little tip about <a href="https://addons.mozilla.org/en-US/firefox/addon/1843/">firebug</a>. Most of you might be aware of this but I found it 3-4 days ago.

Many time when we want to make change in <code>:active</code> and <code>:hover</code> state of anchor link and by default firebug shows styles of default state of anchor link in style tab.


<img src="{{ site.url }}/images/normal-state.gif" alt="Firebug: default state of link">


But here is the way to switch the state default to <code>:hover</code> and <code>:active</code>.

I'm taking this css code for example. and suppose I want test how the link will look in different styles than this

{% highlight css %}
a:link { color:#33F; padding:10px }
a:hover{ background-color:#FC0; color:red }
a:active{ background-color:#CCF; color:green }
{% endhighlight %}

We can test and see live change on page for <code>:hover</code> and <code>:active</code> state using <strong>HTML</strong> panel in firebug. We need to select <code>:active</code> and <code>:hover</code> state from style dropdown in HTML tab.

<code>:hover</code> is selcted in this image. now we can test and see change of <code>a:hover</code> in this condition

<img src="{{ site.url }}/images/hover-selected.gif" alt="Firebug: :hover selected">

style of <code>a:hover</code> is showing on link

<img src="{{ site.url }}/images/hover-state.gif" alt="Firebug: hover state showing">

Same we can do for <code>:active</code> via selecting the :active option

<img src="{{ site.url }}/images/active-selected.gif" alt="Firebug: Active state selected">


style of <code>a:active</code> is showing on link


<img src="{{ site.url }}/images/active-state.gif" alt="Firebug: active state showing on page">

