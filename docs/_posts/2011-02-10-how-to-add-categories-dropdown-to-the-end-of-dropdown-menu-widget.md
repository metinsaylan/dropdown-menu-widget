---
title: >
  How to add categories dropdown to the
  end of Dropdown Menu Widget
tags: ['dropdown menu widget', 'how-to']
---
I recently added hooks to the dropdown menu widget and using those hooks you can enlarge your navigations easily. Here I will show you how to add a categories dropdown to the end of pages menu, as seen on my site.
 ***

We can achieve this simply using `dropdown_list_after` hook. Here is the sample code:


```php
function add_categories(){
  /* Open top level item and sub-list */
  echo &quot;nt&lt;li&gt;&lt;a href=&quot;#cat&quot;&gt;Categories&lt;/a&gt;&lt;ul class=&quot;children&quot;&gt;&quot;;

  /* List categories using wp function*/
  wp_list_categories('title_li=&amp;');

  /* Close sub-list &amp; top level */
  echo &quot;nt&lt;/ul&gt;&lt;/li&gt;&quot;;

  /* You can add your own links too! */
  echo &quot;&lt;li&gt;&lt;a href=&quot;http://metinsaylan.com/&quot;&gt;Shailan.com&lt;/a&gt;&lt;/li&gt;&quot;;

} add_action('dropdown_list_after', 'add_categories');
```


You can easily append anything to the end of list using this simple function.

Enjoy!
