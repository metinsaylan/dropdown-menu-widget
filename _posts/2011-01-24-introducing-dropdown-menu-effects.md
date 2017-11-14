---
title: Introducing dropdown menu effects
tags: ['dropdown menu widget']
---

With the 1.6 update finally added jQuery effects to the dropdown menu widget. This version also brought many other features like, auto-*recognizing dropdown.css in theme folder*, *specifiying an external theme URL*,* options for removing link titles* and *removing links from top-level categories*.
 ***
After a long time finally updated dropdown menu widget to 1.6 (and quickly 1.6.1 to fix things up). In this awesome update (though I know it breaks things all the time) you will find those brand new features:

<ul class="ticks">
<li>**JQuery dropdown effects** - fade in/out & slide down/up,<li>
<li>Auto recognize **dropdown.css** in theme folder,</li>
<li>Specify **external theme URL**,</li>
<li>Option for **removing link title** attributes,</li>
<li>Option for **removing top level links**.</li>
</ul>

<h3>Dropdown menu effects</h3>
To enable dropdown menu effects go to dropdown menu options page and select the effect you want to use. You can also specify a speed for the effect selected.

<a href="{{ site.imgbase }}/2011/01/dropdown-menu-options-page.png"><img src="{{ site.imgbase }}/2011/01/dropdown-menu-options-page.png" alt="" title="dropdown menu options page" width="560" height="439" class="aligncenter size-large wp-image-2074" /></a>

<h3>Dropdown.css</h3>
If you have a custom dropdown theme or if you modified a theme to fit your needs, put it to your theme folder as dropdown.css. Dropdown Menu Widget will look for that file in your theme folder and it will add it to the end of Dropdown Theme selector. You need to save options after you select it as your current theme. (It doesn't automatically use that file.)

<h3>External theme urls</h3>
If you have a custom theme used by multiple sites, you can upload it to one of your sites and specify its URL in the Theme URL text box. To enable this text box make sure to select "From URL" from the theme dropdown. Dropdown will load this file right after core dropdown [CSS](/tag/css/) file.

<h3>Removing link title attributes</h3>
Especially on category dropdowns when you move mouse over a category it displays a tooltip like "View all posts under... " for categories that have no description. If you don't like those tooltips this option is for you. This option removes titles on page load using jquery.

<h3>Removing top level links</h3>
Some users don't want end users to click top leve pages & categories. This option removes links from top level elements and let users click sub menus only.

<a href="{{ site.imgbase }}/2011/01/wp-dropdown-menu-effects.jpg"><img src="{{ site.imgbase }}/2011/01/wp-dropdown-menu-effects.jpg" alt="" title="wp-dropdown-menu-effects" width="514" height="430" class="aligncenter size-full wp-image-2067" /></a>

Let me know what you think of this update in your comments.
