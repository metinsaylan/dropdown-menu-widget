---
title: Dropdown Menu Widget update 1.6.3
tags: ['dropdown menu widget', 'snippets']
---

In this update I fixed dropdown menu arguments problem. Now you can easily add multiple menus using the following syntax.

***

```php
<?php

  $args = array(
    'menu' => 'Header Menu' // Name of your custom menu.
                            // You can also use id or Menu location
  );

  shailan_dropdown_menu( $args );

?>
```

This will show a custom menu you created in **Menus** section with a name **"Header Menu"**.

I will soon write a post about inserting multiple dropdown menus using PHP.

> When you update the plugin, files in the plugin folder are deleted and replaced with new ones by WordPress. If you modified plugin files, you should backup those files before you update.
