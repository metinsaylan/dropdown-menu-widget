---
title: >
  Adding a simple admin menu to dropdown
  menu widget
tags: ['dropdown menu widget']
---
Recently I added some action hooks to <a href="{{ site.baseurl }}/projects/wordpress/dropdown-menu-widget/">dropdown menu widget</a>. Using those hooks you can easily add menu items to the menu and also subscribe buttons or search boxes. Here in this step by step tutorial I will show you how to add a simple administration menu to your dropdown widget.
 ***
This tutorial needs your site have dropdown menu widget installed and working. So if you didn't install it yet you can get it <a href="http://wordpress.org/extend/plugins/dropdown-menu-widget/" rel="nofollow">from here</a>.

To add an admin menu to the widget we will use "dropdown_list_after" action hook. This hook runs right after your menu items so you can add additional list items to the dropdown.

Open "`functions.php`" file in your theme directory and simply add this action hook:

[php light="true" title=""]add_action('dropdown_list_after', 'my_admin_menu');
```


This will tell wordpress to run `my_admin_menu` function to run when `dropdown_list_after` is called.

Now we will create our function called my_admin_menu:


```php
function my_admin_menu(){
  // add admin menu items here
}
```


Before starting admin menu items, it would be better if we checked admin is logged in. Otherwise it will show up to all regular users. We can check it using `current_user_can` wordpress function:
[php light="true" title=""]  if( current_user_can( 'create_users' ) ){ // This should be admin. right?
```


Now that we know current user is admin, we start echoing our menu items:

[php light="true" title=""]  echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/index.php&quot;&gt;Admin&lt;/a&gt;&lt;ul&gt;'; // Start with dashboard on top ;)
```


So this will be our top item. Every unordered list (ul) will be a sub level. Here we started our sublevel items too. Let's go on:


```php
	echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/post-new.php&quot;&gt;Add New..&lt;/a&gt;&lt;ul&gt;';
		echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/post-new.php&quot;&gt;Post&lt;/a&gt;&lt;/li&gt;';
		echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/post-new.php?post_type=page&quot;&gt;Page&lt;/a&gt;&lt;/li&gt;';
		echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/link-add.php&quot;&gt;Link&lt;/a&gt;&lt;/li&gt;';
	echo '&lt;/ul&gt;&lt;/li&gt;';
```


Here we added a branch to add new posts, pages and links. All nested under "Add New.. " top level. Let's add some more admin items:


```php
	echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/themes.php&quot;&gt;Themes&lt;/a&gt;&lt;/li&gt;';
	echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/widgets.php&quot;&gt;Widgets&lt;/a&gt;&lt;/li&gt;';
	echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/plugins.php&quot;&gt;Plugins&lt;/a&gt;&lt;/li&gt;';
```


If you agree that's enough we will close the sub levels. If you like you can continue adding lines to this. After closing sub level &lt;ul&gt; we should close containing li item too.


```php
	echo '&lt;/ul&gt;&lt;/li&gt;';
```


We have done adding items to the menu and now it is automagically dropdown!

Here is the full code for your ease:


```php
function my_admin_menu(){
  if( current_user_can( 'create_users' ) ){ // This should be admin. right?
	// add admin menu items here
	echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/index.php&quot;&gt;Admin&lt;/a&gt;&lt;ul&gt;'; // Start with dashboard on top ;) and start sub items
	echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/post-new.php&quot;&gt;Add New..&lt;/a&gt;&lt;ul&gt;'; // Start another sub level here
		echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/post-new.php&quot;&gt;Post&lt;/a&gt;&lt;/li&gt;';
		echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/post-new.php?post_type=page&quot;&gt;Page&lt;/a&gt;&lt;/li&gt;';
		echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/link-add.php&quot;&gt;Link&lt;/a&gt;&lt;/li&gt;';
	echo '&lt;/ul&gt;&lt;/li&gt;'; // Close 2nd sub level
	echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/themes.php&quot;&gt;Themes&lt;/a&gt;&lt;/li&gt;';
	echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/widgets.php&quot;&gt;Widgets&lt;/a&gt;&lt;/li&gt;';
	echo '&lt;li&gt;&lt;a href=&quot;/wp-admin/plugins.php&quot;&gt;Plugins&lt;/a&gt;&lt;/li&gt;';
	echo '&lt;/ul&gt;&lt;/li&gt;'; // Close the top level
 } // Closing if
}
add_action('dropdown_list_after', 'my_admin_menu');
```


You can also use other hooks registered with the plugin:
<ul>
<li>dropdown_before - Runs in the main container before the div tag containing main dropdown list.</li>
<li>dropdown_list_before - Runs when ul.dropdown is started. You should echo li items.</li>
<li>dropdown_list_after - Runst at the end of dropdown menu. I showed you how to use this hook here.</li>
<li>dropdown_after - Runs after dropdown container is closed.</li>
</ul>

You can find more information about <a href="http://codex.wordpress.org/Function_Reference/add_action">action hooks on wordpress codex.</a>
