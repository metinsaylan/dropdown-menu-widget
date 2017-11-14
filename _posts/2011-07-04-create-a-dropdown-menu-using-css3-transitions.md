---
title: Dropdown Menu Using CSS3 Transitions
layout: post
---

With the most recent developments in the browsers, [CSS](/tag/css/) **shadows**, **transitions** and **animations** made popular amongst **web site design.** So I decided to create a basic tutorial on how to create a simple **dropdown menu** using those brand new attributes. Let's start!

 ***

<a href="{{ site.imgbase }}/2012/04/CSS3-dropdown-menu-preview.jpg"><img class="aligncenter size-full wp-image-3220" title="CSS3-dropdown-menu-preview" src="{{ site.imgbase }}/2012/04/CSS3-dropdown-menu-preview.jpg" alt="" width="660" height="214" /></a>

<a class="button demo large" href="{{ site.baseurl }}/demos/css3-transitions-dropdown.html">View Demo</a>

<a class="button download large" href="{{ site.baseurl }}/demos/css3-dropdown.css">Download Source</a>

## 1. HTML

All dropdown menus use the same HTML structure. An unordered list surrounded with a wrapper. This works with most browsers when alignment is not an issue. So here is the most basic dropdown structure:


```php
<div id="navigation">
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a>
      <ul>
        <li><a href="#">Web design</a></li>
        <li><a href="#">Wordpress</a></li>
      </ul>
     </li>
    <li><a href="#">Contact</a></li>
  </ul>
</navigation>
```

If you are using WordPress, you can either type your own menu or you can use a basic list generating function like `wp_page_menu`. Here is a sample code for generating a pages list in WordPress:

```php
<div id="navigation" class="clearfix">
<?php
	$args = array(
		'show_home'   => true,
		'depth'        => 0,
		'child_of'     => 0,
		'title_li'     => '',
		'echo'         => 1,
		'sort_column'  => 'menu_order, post_title',
		'link_before'  => '',
		'link_after'   => ''
		);

	wp_page_menu( $args );
?>		
</div>
```

***

## 2. Dropdown Basics

We will start by removing list attributes from the unordered list and make it display inline. This is much like a reset [CSS](/tag/css/) rule.

```css                       
#navigation ul,#navigation li { list-style:none; padding:0; margin:0; display:inline; }
```

We also need to add relative positioning and float to the list items. Sub level lists will have position absolute attributes. So position relative will make sure that the sub levels obey their top level only:

```css                       
#navigation ul li{ float:left; position:relative; }                       
```                    

If you view current setup with a browser you will see all list items inline with no space in between: "HomeAboutServicesContact". We will add this space by adding block attributes to list anchor items:

```css                       
#navigation ul li a{
	display:block;
	padding:3px 6px;
	margin:1px;
	font-size:12px;
	white-space:nowrap;
}                       
```                    

"white-space:nowrap;" makes sure our list items won't wrap, and the list size will enlarge to fit in. Otherwise long items in our menu would display as multi-lines.

Let's position our sub levels and style them as needed. We will reach them using "#navigation ul ul". This selector means, select the second "ul" under "#navigation" which is our sub level.

```css                       
#navigation ul ul{
	position:absolute;
	top:-99999px;    /* Remove them out of viewport */
	left:0;  
	opacity: 0;      /* Hide sub level, we will use this in transition */
	-webkit-transition: opacity .4s ease-in-out; /* For chrome &amp; safari */
	-moz-transition: opacity .4s ease-in-out; /* For mozilla firefox */
	-o-transition: opacity .4s ease-in-out; /* For opera */
        transition: opacity .4s ease-in-out; /* Not yet implemented, but will be available soon */
	z-index:497;
	background:#333;
	padding: 2px;
	border:1px solid #444;
	border-top:none;
	box-shadow:#111 0 3px 4px; /* Shadows make menus more beautiful */
	border-bottom-left-radius:6px;
	border-bottom-right-radius:6px;
}                       
```                    

The most important part of this dropdown menu is the transition property;

```css
transition: opacity .4s ease-in-out;                       
```                    

This code tells the browser that, when **opacity** value changes in this element, use a **.4 second** **fade-in-out** effect. You can change time period and also timing function in this code. Possible values for timing functions are linear, ease, ease-in, ease-out, ease-in-out and cubic-bezier(n,n,n,n).

Our code is almost ready, but second level sub menus will appear below first level dropdown menus, so we need to change second level's positioning a little:

```css                       
#navigation ul ul ul {
	position:absolute;
	top:-99999px;
	left:100%;
	border-radius:6px;
	border:1px solid #444;
}                       
```                    

Now that we added all the styling we need. We need a trigger, to make the magic happen. That is the hover effect:

```css                       
#navigation ul li:hover>ul{ opacity: 1; position:absolute; top:99%; left:0; }
#navigation ul ul li:hover>ul{ opacity: 1; position:absolute; top:0; left:100%;  }                       
```                    

When someone move mouse over a "li" (list item), we turn opacity value to 1 and change position of the submenu so that it will fade in slowly using the transition property.

***

## 3. Full code

For those who like ready-to-copy codes, here is the full code:

```css                       
div#navigation{
	background: #444444; /* Old browsers */
	border-radius: 4px;
}
#navigation ul, #navigation li{ list-style:none; padding:0; margin:0; display:inline; }
#navigation ul li{ float:left; position:relative; }
#navigation ul li a{
	display:block;
	padding:8px 12px;
	margin:1px;
	font-size:18px;
	white-space:nowrap;
	border-radius:3px;
}
#navigation ul li a:hover{ background:#222;}
#navigation ul ul{
	position:absolute;
	top:-99999px;
	left:0;
	opacity: 0; /* Hide sub level */
	-webkit-transition: opacity .5s ease-in-out;
	-moz-transition: opacity .5s ease-in-out;
	-o-transition: opacity .5s ease-in-out;
	z-index:497;
	background:#333;
	padding: 2px;
	border:1px solid #444;
	border-top:none;
	box-shadow:#111 0 3px 4px;
	border-bottom-left-radius:6px;
	border-bottom-right-radius:6px;
}
#navigation ul ul ul {
	position:absolute;
	top:-99999px;
	left:100%;
	opacity: 0;
	-webkit-transition: opacity .5s ease-in-out; /* Hide sub levels */
	-moz-transition: opacity .5s ease-in-out;
	-o-transition: opacity .5s ease-in-out;
	border-radius:6px;
	border:1px solid #444;
}
#navigation ul li:hover>ul{ opacity: 1; position:absolute; top:99%; left:0; }
#navigation ul ul li:hover>ul{ position:absolute; top:0; left:100%; opacity: 1; z-index:497; background:#333; }                       
```                    

***

## 4.Conclusion

If you want to create a very lightweight dropdown menu for your site, CSS3 is the key. It is just a block of code and you don't need any JavaScript code at all! Using those brand new css3 properties, you can achieve great design elements.
