---
published: true
title: Change Currency Symbol in Woocommerce
categories: 'WordPress, WooCommerce, Currency'
layout: post
date: 2020-10-23T18:06:34.000Z
excerpt_separator: <!--more-->
---
If you are like me who have some clients that want to change their online store's currency symbol, then  you are in the right place.

Add the below code snippet in your child theme's `functions.php`. It will work as long as your site is running **WordPress** and **WooCommerce**

<!--more-->

```php

add_filter('woocommerce_currency_symbol', 'themename_change_currency_symbol', 10, 2);

function themename_change_currency_symbol( $currency_symbol, $currency ) {
	switch( $currency ) {
		case 'SAR':
			$currency_symbol = 'SR';
			break;
	}
	return $currency_symbol;
}

```
