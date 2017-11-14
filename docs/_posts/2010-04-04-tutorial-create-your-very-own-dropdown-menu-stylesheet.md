---
title: 'Tutorial: Create your very own dropdown menu stylesheet'
---

I’ve created a very simple plugin for creating and adding **dropdown menu**s to your page. In this simple step-by-step tutorial I will try to explain **how to create your own theme with simple css** edits. All you need to do is to follow those simple steps and you will have one great css-only dropdown with colors you like!
 ***
***

<span class="alt">1</span> First we need to set default theme to NONE for the dropdown menu. You can do that from the “Dropdown Menu” item under your Wordpress Settings.

<a title="dropdown-css-tutorial-1" rel="lightbox[655]" href="{{ site.imgbase }}/dropdown-css-tutorial-1.jpg" target="_blank"><img title="dropdown-css-tutorial-1" alt="" src="{{ site.imgbase }}/dropdown-css-tutorial-1.jpg" width="300" height="172" class="aligncenter" /></a>

***
<span class="alt">2</span> Then open your theme stylesheet from Appearance -&gt; Editor. Make sure your current theme is selected. Select Stylesheet from Styles and scroll to the bottom of the file. You can add a reminder using /* and */ slashes as in the image. We will create our [CSS](/tag/css/) rules after this line.
<a title="dropdown-css-tutorial-2" rel="lightbox[655]" href="{{ site.imgbase }}/dropdown-css-tutorial-2.jpg" target="_blank"><img title="dropdown-css-tutorial-2" alt="" src="{{ site.imgbase }}/dropdown-css-tutorial-2.jpg" width="300" height="172" /></a>

***
<span class="alt">3</span> Dropdown menu [CSS](/tag/css/) tree is defined in following way.
[css].shailan-dropdown-menu -&amp;gt; main container of the menu (div element)
ul.dropdown -&amp;gt; top list
ul.dropdown li -&amp;gt; top list item + sub items (refers to &amp;lt;li&amp;gt; elements under &amp;lt;ul&amp;gt;)
ul.dropdown li a -&amp;gt; menu links
ul.dropdown li ul -&amp;gt; sub lists[/css]

***
<span class="alt">4</span> First we add a background image to top level using the .shailan-dropdown-menu class:

```
.shailan-dropdown-menu { background:#000000 url("your-image-here.jpg") top right repeat; }
```

"#000" defines background color to be black. <a href="{{ site.imgbase }}/html-color-codes.png" target="_blank">Look here for more html color codes</a>. Your background image should be in your theme directory. Otherwise you should put a full url like “http://metinsaylan.com/sample.jpg”. Other k-words define positioning and repeating of background. <a rel="nofollow" href="http://www.w3schools.com/css/css_background.asp" target="_blank">Visit here for more info on background</a>.

***
<span class="alt">5</span> Second most important thing on the menu style is the link style:
[css].shailan-dropdown-menu ul.dropdown li a {
	padding: 5px 15px;
	font-size: 1em;
	color:#ffffff; }[/css]
Here we defined top-bottom (5px) and right-left (15px) padding values. And we set color to white.

***
<span class="alt">6</span> Now let’s define the mouse over style for the links:
[css].shailan-dropdown-menu ul.dropdown li a:hover {
	font-style: italic;
	background-color:#ffffff;
	color:#333333; }[/css]
This rule defines that when we move mouse over (hover) a link (&lt; a &gt; element in html) it will have white (#ffffff) background color and text will be a dark gray (#333333). Text will become italic also.

***
<span class="alt">7</span> One more additional style will be dropdown background:
[css]	.shailan-dropdown-menu ul.dropdown li ul{ width:auto; background:#333333; background: url(images/opacity.png);
		border-radius: 4px;
		-moz-border-radius: 4px;
		-webkit-border-radius: 4px;
		-khtml-border-radius: 4px; }[/css]
This is a rather complex rule. This rule defines background for the dropdown menu’s when you move over a link. Here we set it to have a gray(#333333) background. Then we put a background image to it. Transparent pixels don’t work in older Internet Explorer browsers. You should get <a rel="nofollow" href="http://google.com/chrome" target="_blank">Google chrome</a> really if you are still using IE. Here we also add corner radius which is also not supported by Internet Explorer.

***
<span class="alt">8</span> The last style rule comes for the current page or category link. If you want current page or category seem different than other links add following:
<pre class="brush:css">.shailan-dropdown-menu ul.dropdown li.current_page_item&gt;a,
	.shailan-dropdown-menu ul.dropdown li.current-cat&gt;a,
	.shailan-dropdown-menu ul.dropdown li.current-cat&gt;a:hover,
	.shailan-dropdown-menu ul.dropdown li.current_page_item&gt;a:hover{
	color:#333333;
	background: white; }
```

This will make your current page/category have a white background with dark gray text.

***
<span class="alt">9</span> Now to wrap it up here is the final code:
<pre class="brush:css">/* MY-DROPDOWN-STYLES */
.shailan-dropdown-menu { background:#000000 url("your-image-here.jpg") top right repeat; }
.shailan-dropdown-menu ul.dropdown li a {
	padding: 5px 15px;
	font-size: 1em;
	color:#ffffff; }
.shailan-dropdown-menu ul.dropdown li a:hover {
	font-style: italic;
	background-color:#ffffff;
	color:#333333; }
.shailan-dropdown-menu ul.dropdown li ul{ width:auto; background:#333333; background: url(images/opacity.png);
		border-radius: 4px;
		-moz-border-radius: 4px;
		-webkit-border-radius: 4px;
		-khtml-border-radius: 4px; }
.shailan-dropdown-menu ul.dropdown li.current_page_item&gt;a,
	.shailan-dropdown-menu ul.dropdown li.current-cat&gt;a,
	.shailan-dropdown-menu ul.dropdown li.current-cat&gt;a:hover,
	.shailan-dropdown-menu ul.dropdown li.current_page_item&gt;a:hover{
	color:#333333;
	background: white; }
```

And we are done!

***
<h4>Conclusion</h4>
Now that you know how to create a simple dropdown menu style, you can <a href="{{ site.baseurl }}/projects/wordpress/dropdown-menu-widget/" target="_blank">download the widget</a> and **start building your own menu theme!**
