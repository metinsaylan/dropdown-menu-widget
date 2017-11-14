---
title: Dropdown Menu - PHP Template Tag Usage Explained
tags: ['dropdown menu widget']
---

**Dropdown menu widget** is so easy to use as a **widget**, but it also **supports usage of PHP template tags**. Using PHP code to insert the menu, you can easily add menus to your theme as many times as you like. In this post, I will show you different **code snippets to add the widget** to your theme easily.

***

### Default usage
Adding dropdown menu widget using PHP is so easy. If you are going to add just one menu, things get a lot easier. All you have to do is to insert:

```php
<?php shailan_dropdown_menu( ); ?>
```

somewhere in your `header.php` template. This is the default usage. This template tag uses settings page to get the necessary information. So after you add this code, you can easily change your menu options in the Dropdown Menu Widget options page.

***

### Adding pages menu
To add a dropdown menu of your pages, you can use:

```php
<?php shailan_dropdown_menu( array( 'menu' => 'pages' ) ); ?>
```

code. This snippet will get all the other data from the template tag options page except the menu type.

***

### Adding categories menu

To add categories dropdown, you can use:

```php
<?php shailan_dropdown_menu( array( 'menu' => 'categories' ) ); ?>
```

code. This snippet will also get all the other data from the template tag options page except the menu type.

***

### Adding a custom menu using php code

To add a custom menu you created you need to set menu variable to either its ID or its name. Here are some examples:

```php
<?php shailan_dropdown_menu( array('menu'=>'Katalog') ); // Adds a custom menu named Katalog ?>

<?php shailan_dropdown_menu( array('menu'=>'439') ); // Adds a custom menu with id 438 ?>
```

You can add as many as you like. There is no limit on the number of menus you can add.

***

### Full arguments template

If those are not enough for your requirements here is the full arguments list. You can create many different menus using this argument template. Just change the variables as you need:

```php
<?php // SETUP
$args =array(
	'menu' => 'pages',			// Menu type pages | categories | menuID | menu name
	'exclude' => '21,35,438',	// IDs of pages to be excluded
	'login' => true,			// Display login/logout link?
	'admin' => false,			// Show site admin link?
	'vertical' => false,		// Display vertical?
	'home' => true,				// Display home link?
	'align' => 'right',			// Align left | center | right
	'width' => '500'			// Width of menu
);
// CREATE
shailan_dropdown_menu( $args ); ?>
```

***

### Conclusion

**Dropdown menu widget** allows you to easily manage your menus. It **automatically generates menu code, effects and even [CSS](/tag/css/) styles**. All you need is to add it and then edit your menu as you like. Using template tag's powers, now you can add multiple dropdown menus to your site, even if you don't have any sidebars. In this post, I showed you most common uses of the template tag. I hope you find it useful.
