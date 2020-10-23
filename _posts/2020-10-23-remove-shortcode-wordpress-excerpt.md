---
published: true
title: Remove Shortcodes from WordPress Excerpts
categories: WordPress
layout: post
date: 2020-02-10T10:00:00.000Z
excerpt_separator: <!--more-->
---
If you are a theme developer, you may have encounter that shortcodes appear also on your posts excerpts. You can use the code below to remove the shortcode.

<!--more-->

```php
add_filter('the_excerpt', 'strip_shortcode_from_excerpt');

function strip_shortcode_from_excerpt( $content ) {
    if ( is_home() ) {
        $content = strip_shortcodes( $content );
    }
    return $content;
}
```

This works if the current page is your blog home. If you want it to work, remove the if conditions like below:

```php
function strip_shortcode_from_excerpt( $content ) {
	$content = strip_shortcodes( $content );
    return $content;
}
```