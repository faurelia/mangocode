---
published: true
title: Change Currency Symbol in Woocommerce
categories: 'WordPress, WooCommerce, Currency'
layout: post
date: 2020-10-23T18:06:34.000Z
excerpt_separator: <!--more-->
---

If you are looking for a way to change your online store's currency symbol, add the below code snippet in your child theme's `functions.php`
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
