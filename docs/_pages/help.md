---
layout: page
title: Dropdown Menu Widget Help
desc: Descriptions for the options and widget inputs
permalink: /help/
---

<h2 id="options-page">Options page</h2>

<h3 id="rename-homepage">Rename Homepage</h3>
<p>You can change home page link text here. It defaults to Home in your language. If you enter a text it will be displayed instead.</p>

<h3 id="parent-indicators">Parent Indicators</h3>
<p>Parent indicators are small arrows displayed next to menu items that has a sub menu. You can turn them on/off using this check box. <strong>To remove arrows</strong> just uncheck this option.</p>

<h3 id="indicator-color">Indicator Color</h3>
<p>Indicator color defaults to dark gray. However you can define custom colors using this text box. It will allow HEX, rgb and rgba colors. For example #ff0000 will display red pointers. You can also use <code>rgba(255,255,255,0.3)</code> (transparent white) style colors. </p>

<h3 id="wrap-long-menu-items">Wrap long menu items</h3>
<p>Sub menu items may be long sometimes. Dropdown menu by default doesn’t wrap long items, so they appear as a long line. If you have very long sub menu items you may want to turn this option on.</p>

<h3 id="remove-title-attributes">Remove title attributes</h3>
<p>WordPress by default adds title attributes to all category items (eg. “View all posts categorized..”). Those titles appear as a tooltip when a user moves over your links. When you turn this option on, drop down menu widget uses a jQuery hack to remove those title attributes from drop down menu links.</p>

<h3 id="remove-links-from-top-levels">Remove links from top levels</h3>
<p>This option removes links from menu items that has a sub menu.</p>

<h3 id="enable-dropdown-effects">Enable dropdown effects</h3>
<p>Dropdown menu widget supports jQuery effects slide down and fade. If you turn this option on menu will use jQuery to slide down items instead of css.</p>

<h3 id="effect">Effect</h3>
<p>If effects are enabled, you can select one of the effects. Effects are using jQuery, if dropdown doesn’t work with effects turned on, you may have some problem with your jQuery version.</p>

<h3 id="effect-speed">Effect speed</h3>
<p>This option sets how fast your sub menus will appear. There are three effect speed options: normal, slow, fast.</p>

<h3 id="effect-delay">Effect delay</h3>
<p>This option sets how much time menu waits before dropdown sub menu items appear. This option uses hoverIntent jquery plugin to delay the effect.</p>

<h3 id="menu-theme">Menu theme</h3>
<p>Dropdown menu has various built-in themes. You can select one of them using this drop down. If you select From URL, you can specify link to a style sheet below. If you have drop down.css in your theme root, it will be displayed in this dropdown, so you can select it. Same applies for template directory in child themes.</p>

<h3 id="theme-url">Theme URL</h3>
<p>If <code>From URL</code> is selected as theme, you can specify its URL here in this field. Dropdown includes that CSS file to be used, so you don’t need to edit your header file.</p>

<h3 id="use-custom-colors">Use custom colors</h3>
<p>This option enables use of custom colors specified in the fields below. Custom colors works best with Custom Color Scheme theme, with other themes it may not work as expected.</p>

<h3 id="menu-background-color">Menu background color</h3>
<p>If custom colors are enabled, you can specify a menu background color code in this field. It allows hex values only.</p>

<h3 id="hover-background-color">Hover background color</h3>
<p>If custom colors are enabled, you can specify a menu item hover color here. It allows hex values only.</p>
