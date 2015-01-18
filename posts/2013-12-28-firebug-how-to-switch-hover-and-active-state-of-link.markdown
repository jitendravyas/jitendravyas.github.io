---
layout: post
title: 'Firebug tip: How to switch :hover and :active state of link to see live changes?'
date: 2013-12-28 09:38:57.000000000 +05:30
---
<img class="alignnone size-full wp-image-30" title="firebug-tip" src="/content/images/2010/Sept/firebug-tip.gif" alt="Firebug: A useful tool for web development" width="560" height="144" />

Here I'm sharing a little tip about <a href="https://addons.mozilla.org/en-US/firefox/addon/1843/">firebug</a>. Most of you might be aware of this but I found it 3-4 days ago.

Many time when we want to make change in <code>:active</code> and <code>:hover</code> state of anchor link and by default firebug shows styles of default state of anchor link in style tab.

<img class="size-full wp-image-35" title="normal-state" src="/content/images/2010/Sept/normal-state.gif" alt="default state of link" width="515" height="220" />

But here is the way to switch the state default to <code>:hover</code> and <code>:active</code>.

I'm taking this css code for example. and suppose I want test how the link will look in different styles than this

<pre escaped="true" lang="css" line="1">
a:link { color:#33F; padding:10px }
a:hover{ background-color:#FC0; color:red }
a:active{ background-color:#CCF; color:green }</pre>

We can test and see live change on page for <code>:hover</code> and <code>:active</code> state using <strong>HTML</strong> panel in firebug. We need to select <code>:active</code> and <code>:hover</code> state from style dropdown in HTML tab.

<code>:hover</code> is selcted in this image. now we can test and see change of <code>a:hover</code> in this condition

<img class="size-full wp-image-33" title="hover-selected" src="/content/images/2010/Sept/hover-selected.gif" alt=":hover selected" width="239" height="163" />

style of <code>a:hover</code> is showing on link

<img class="size-full wp-image-34" title="hover-state" src="/content/images/2010/Sept/hover-state.gif" alt=":hover state showing" width="561" height="240" />

Same we can do for <code>:active</code> via selecting the :active option

<img class="size-full wp-image-31" title="active-selected" src="/content/images/2010/Sept/active-selected.gif" alt="Active state selected" width="262" height="183" />

style of <code>a:active</code> is showing on link

<img class="size-full wp-image-32" title="active-state" src="/content/images/2010/Sept/active-state.gif" alt=":active state showing on page" width="581" height="314" />

Please write your thoughts in comment about this post
