---
title: >
  How to change dropdown menu depth and
  order using filters
tags: ['dropdown menu widget', 'how-to']
---

With the 1.5.8 release, I added dropdown_menu_defaults filter to the <a href="{{ site.baseurl }}/projects/wordpress/dropdown-menu-widget/">dropdown menu widget</a>, so anyone can edit dropdown menu defaults so easily. Here in this post I will show you how to change depth and page order using this filter.

 ***

First open `functions.php` in your theme folder and add those lines:

[php title="functions.php"]function my_dropdown_defaults($menu){
  // Change settings here
  return $menu; // return the variable array back
} add_filter( 'dropdown_menu_defaults', 'my_dropdown_defaults' );
```


This is the basic structure of a filter. We attach this filter to a tag called `dropdown_menu_defaults` so whenever this filter is called our function will run.

Next step we will change depth of menu. By default, depth is 4, here I will limit it to 2, so that only one level dropdown will show up. We can do it easily adding this line

[php title="functions.php" highlight="3"]function my_dropdown_defaults($menu){
  // Change settings here
  $menu['depth'] = 2;
  return $menu; // return the variable array back
} add_filter( 'dropdown_menu_defaults', 'my_dropdown_defaults' );
```


Now let's change order of the pages on the menu. Dropdown menu widget uses <a href="http://codex.wordpress.org/Function_Reference/wp_list_pages#Default_Usage" target="_blank">wp_list_pages defaults</a> to list your pages. So any setting you see on the codex page is acceptable for the dropdown. Let's sort pages by IDs:

[php title="functions.php" highlight="4"]function my_dropdown_defaults($menu){
  // Change settings here
  $menu['depth'] = 2;
  $menu['sort_column'] = 'ID';
  return $menu; // return the variable array back
} add_filter( 'dropdown_menu_defaults', 'my_dropdown_defaults' );
```


Now whenever a dropdown is generated this function will set depth to 2 and change sort column to page ids.

Please note that this example is given for pages menus. For category dropdowns you need to use wp_list_categories defaults and for wp3 custom menus you have to use wp_nav_menu defaults. Generally defaults like order, depth, and sort_column remain same, but you may find differences between arguments.

Btw. I also added a <a href="{{ site.baseurl }}/projects/wordpress/dropdown-menu-widget/menu-themes/">dropdown menu themes page</a> so you can view all themes without switching anything. <a href="{{ site.baseurl }}/projects/wordpress/dropdown-menu-widget/menu-themes/">Check them out here</a>.

Cheers.
