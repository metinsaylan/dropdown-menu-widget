---
layout: page
title: Dropdown Menu Widget Troubleshooter
desc: Having problems with dropdown menu widget?
permalink: /troubleshooter/
---

<h4>Sub menus do not align with the menu</h4>
This is generally caused by CSS rule that gives submenus a constant width. To remove that constant width of submenus, simply put following code in your Custom CSS area in the options page:

```css
ul.dropdown ul { width: auto !important; }
```

 ***

<h4>Part of submenus not visible</h4>

The container element may have <code>overflow:hidden</code> in CSS code. This cuts overflowing elements and they are only partly visible. Try removing overflow attribute from the container element.

 ***

<h4>Sub lists can be seen in the source code of the page, but dropdown menu doesn't work</h4>

This is generally caused by themes changing jquery code. Try disabling effects, if that works it means your jquery version is changed by your theme. If it still doesn't work you need a wp_footer call in your footer.php file.

 ***

<h4>I checked home link on options page, but it doesn't appear on my menu</h4>

You are probably using Custom menus. For custom menus you have to add "Home" item from Pages in the Wordpress "Menus" page. Plugin doesn't add any custom links (home/admin/register) to the menu for Custom Menus.

 ***

<h4>Home checkbox is checked but I don't see Home Link on the menu?</h4>

If you are using a wordpress menu you have to add it to your menu yourself.

 ***

<h4>How can I sort / change order of items in my menu?</h4>
You can only do this if you are using Appearance->Menus to define your menus. Automatically generated menus (Categories and Pages) can not be sorted.

 ***

<h4>Your problems not solved?</h4>

Please submit your issue on Github.
