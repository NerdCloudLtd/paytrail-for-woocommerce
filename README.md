# Paytrail for WooCommerce
[Paytrail](https://www.paytrail.com) payment service for [WooCommerce](https://www.woocommerce.com)

**Required WordPress version:** 4.9<br>
**Required WooCommerce version:** 3.5<br>
**Required PHP version:** 7.3

**[Paytrail](https://www.paytrail.com)** is a payment gateway that offers 20+ payment methods for Finnish customers.

The payment gateway provides all the popular payment methods with one simple integration. The provided payment methods include but are not limited to credit cards, online banking and mobile payments.

To use this extension, you need to sign up for a Checkout Finland account. Transaction fees will be charged for every transaction. Transaction cost may vary from merchant to merchant, based on what is agreed upon with Checkout Finland when negotiating your contract. For more information and to register, please visit [our website](https://www.paytrail.com) or contact [asiakaspalvelu@paytrail.com](mailto:asiakaspalvelu@paytrail.com) directly.

We employ the industry's best security practices and tools to maintain bank-level security for merchants and end customers. Paytrail is PCI DSS Level I and GDPR compliant. 

Upon checkout, customers are redirected to the Paytrail payment service. The customer enters his or her payment information directly into our secure environment so that the web shop never comes into contact with the customers payment data. Once the payment process is complete, customers will redirected back to your store. Tokenization is used to run transactions with stored payment information. No confidential card data is ever stored on your server.

## Installation

### From WordPress plugin directory

Open WordPress Admin panel and go to Plugins -> Add New. Search for [Paytrail for WooCommerce](https://wordpress.org/plugins/paytrail-for-woocommerce/), click install and then activate. 

After installation go to WooCommerce -> Settings -> Payments and select "Manage" next to Paytrail for WooCommerce to review settings.

### Via Composer

1. If you have Composer installed:
- You can use the command line to install the plugin:

```
$ composer require paytrail/paytrail-for-woocommerce
```
- Or you can add the following json to your `composer.json` file:

```json
{
  "require": {
    "paytrail/paytrail-for-woocommerce": "*"
  }
}
```
2. Activate the plugin.
3. Go to WooCommerce Settings and open Payments tab.
4. Enable Paytrail for WooCommerce with the toggle switch.
5. Configure your own Checkout Finland payment service settings.

## Configuration

There are several settings you can configure via the options page.

### Test mode

If test mode is enabled, your store will automatically use Paytrail's [test credentials](https://paytrail.github.io/api-documentation/#/?id=test-credentials).

### Debug log

Enable logging all payment gateway events. Recommended only for debugging purposes as this might save personal data.

### Payment provider selection

Choose whether you want the payment provider selection to happen on the checkout page or on a separate page.

### Merchant ID and Secret key

Your Paytrail credentials. You can obtain the keys by registering at our [website](https://www.paytrail.com) or contact [asiakaspalvelu@paytrail.com](mailto:asiakaspalvelu@checkout.fi) directly.

### Fallback Country

Setup fallback country to be used if no country is provided from Woocommerce checkout. Use only if billing_country/shipping_country is removed from checkout fields.

## Router

### Callback Routes

Permalinks enabled:

    Success: /paytrail-payment-service/callback/index
    Cancel: /paytrail-payment-service/callback/index

Permalinks disabled:

    Success: /index.php?paytrail-payment-service-route=callback&paytrail-payment-service-action=index
    Cancel: /index.php?paytrail-payment-service-route=callback&paytrail-payment-service-action=index
