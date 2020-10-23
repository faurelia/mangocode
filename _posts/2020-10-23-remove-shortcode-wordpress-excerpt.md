---
published: true
title: Remove Shortcodes from WordPress Excerpts
categories: WordPress
layout: post
date: 2020-10-23T10:00:00.000Z
excerpt_separator: <!--more-->
---

If you are a theme developer, you may have encounter that shortcodes appear also on your posts' excerpts. 

This mostly happens in your blog home or archive pages, where posts are displayed in a loop.

Below is a code snippet that you can hook to WordPress before your posts are displayed.

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