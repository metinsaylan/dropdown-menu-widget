---
title: 'Dropdown Menu Widget Update: 1.4.0'
tags: ['dropdown menu widget']
---

I made two updates to the <a href="{{ site.baseurl }}/projects/wordpress/dropdown-menu-widget/">dropdown menu widget</a>. Here are the updates:

***

<ol>
	<li>Fix IE display errors. This support is added using jQuery. So it should work with every WordPress installation. Since IE doesn't support hover pseudo class for li elements I added a simple javascript to add `.hover` class when you mouse over them. I tested it on my site with IE8 and it is working now. Not tested with older IE versions though.</li>
	<li>Second update is about wrapping menu items. As you see on my menu items with long text on it like "Dropdown Menu Widget" make menu large and some people don't like this view. That's why I added option for no-wrap. Now you can easily change this wrapping behavior from your options panel. (Note: This behavior is limited for certain themes only.)</li>
</ol>

And here is a list of things I want to add to the next versions

<ol>
	<li>Support for <a href="http://codex.wordpress.org/Version_3.0" target="\_blank">Wordpress 3.0</a> menu &amp; navigation system,</li>
	<li>Theme edit screen,</li>
	<li>Visual theme selection,</li>
	<li>z-index option.</li>
</ol

You can <a href="http://downloads.wordpress.org/plugin/dropdown-menu-widget.zip">download the latest version</a> of the dropdown menu widget here.

That's all for now. If you like this plugin please <a href="{{ site.baseurl }}/donate/">support</a> its development. Thanks!
