=== WooCommerce Steem Payment Method ===
Contributors: sagescrub, recrypto
Donate link: https://steemit.com/@sagescrub
Tags: woocommerce, woo commerce, payment method, steem, sbd
Requires at least: 4.1
Tested up to: 4.9.8
Stable tag: 1.0.10
Requires PHP: 5.2.4
License: GPLv3
License URI: https://www.gnu.org/licenses/gpl-3.0.html

Accept STEEM or SBD payments in your WooCommerce store via SteemConnect. Automatically converts from fiat (USD, EUR, etc) to STEEM. No transaction fees.

== Description ==

WooCommerce Steem Payment Method lets you accept Steem payments directly to your WooCommerce shop (Currencies: STEEM, SBD).

= Details =

* There is no extra transaction fee. Payments are made directly between customer and store owner via SteemConnect. 
* This plugin will automatically detect if payment was made once it is posted to Steem Blockchain. 
* If payment is not completed within several minutes of submitting an order an automatic payment reminder email will be sent to the customer with instructions for submitting payment. This is a fallback for 1) the customer doesn't complete the transaction, and 2) the payment detection functionality in this plugin stops working for any reason.
* Currency exchange rate between FIAT and STEEM/SBD is automatically calculated at time of checkout.
* Currency exchange rate between FIAT and STEEM/SBD can be optionally displayed below the product price on the product page.

= Supported Steem Currencies =
- Steem (STEEM)
- Steem Backed Dollars (SBD)

= FIAT Currencies Supported =
- Currently supports fiat currencies such as: AUD, BGN, BRL, CAD, CHF, CNY, CZK, DKK, GBP, HKD, HRK, HUF, IDR, ILS, INR, JPY, KRW, MXN, MYR, NOK, NZD, PHP, PLN, RON, RUB, SEK, SGD, THB, TRY, ZAR, EUR
- If none of the fiat currency listed above, it will default 1:1 conversion rate between your store's currency and STEEM or SBD.

= Security Note =
You will <strong>NOT</strong> require any Steem keys for this plugin to work. You just have to provide your Steem username and you're good to go.

= Thanks =
Special thanks to [@ReCrypto](https://steemit.com/@arcange) for being the author and inventor of the original "WooCommerce Steem" plugin before it was forked and updated into this plugin "WooCommerce Steem Payment Method". Thank you @ReCrypto for sharing your hard work!

= Disclaimer =
Authors claim no responsibility for missed transactions, loss of your funds, loss of customer funds, incorrect or delayed exchange rates or any other issue you may encounter as a result of using this plugin. Use this plugin at your own risk.

== Installation ==

1. Upload the plugin files to the `/wp-content/plugins/woocommerce-steem-payment-method` directory, or install the plugin through the WordPress plugins screen directly.
1. Activate the plugin through the 'Plugins' screen in WordPress
1. Turn on Steem as a payment method in WooCommerce->Settings->Payments. Turn on the "Enabled" switch.
1. Update settings for this plugin in WooCommerce->Settings->Payments and clicking "Manage" next to "Steem"
1. Make sure to put your Steem username in the "Payee" box so that you will receive payments.

== Frequently Asked Questions ==

= How is customer payment made? =
When the customer initiates payment the SteemConnect window will be opened (see screenshot). SteemConnect will be populated with the payment amount, currency and memo. The automatically generated memo is a random key that is matched to the order.

= How does it confirm Steem Transfers? =
It uses queries the store's STEEM wallet history every 5 minutes to and checks for a transaction that matches the payment MEMO, amount and currency (STEEM or SBD). When the matching payment is found, the order is marked from "payment pending" to "processing".

= What is the payment reminder email? =
If the customer does not complete the payment via SteemConnect within several minutes of initiating the payment, a confirmation email will be sent reminding the customer to make payment manually via steem (see screenshot). The payment reminder email will include instructions including the memo.

= How can I support this plugin? =
Please support me by following me on Steem [@sagescrub](https://steemit.com/@sagescrub) or if you feel like donating, that would really help a lot on my future efforts with this plugin.

If you are a developer and would like to contribute, please let me know!

Steem: @sagescrub

== Screenshots ==

1. Product page showing optional exchange rate below product price.
2. Steem payment method option on checkout page. Customer can choose between STEEM or SBD currencies. Exchange rate from FIAT is calculated automatically.
3. SteemConnect for processing payment. Note memo that is provided will be used to match the order.
4. Payment not received reminder email.
5. Payment method in WooCommerce
6. Settings for this plugin within WooCommerce Payments Settings

== Changelog ==

= 1.0.10 - 2018-10-23 =
* Updated deprecated WooCommerce functions

= 1.0.9 - 2018-10-23 =
* Updated pending payment emails to use WC_Email class for sending

= 1.0.8 - 2018-10-22 =
* Fixed order receipt not displaying steem transaction details correctly.

= 1.0.7 - 2018-10-10 =
* STEEM, SBD currencies now allowed as WooCommerce store currency.
* Sending payment to same STEEM wallet will now register as payment received. Helpful for testing order flow.

= 1.0.6 - 2018-09-05 =
* New version in WordPress Plugin Repository named "WooCommerce Steem Payment Method" (forked from WooCommerce Steem)
* Added auto payment reminder email
* Added SteemConnect into payment flow
* Updated the auto payment matching feature to use a different API since previous API (SteemSQL) is no longer freely available
* Fixed Null reference error that would not show exchange rate for order total when the checkout page first loads.

