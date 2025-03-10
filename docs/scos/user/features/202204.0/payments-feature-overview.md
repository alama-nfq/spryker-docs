---
title: Payments feature overview
description: Orders can be paid with none, one or multiple payment methods that can be selected during checkout. Offer multiple payment methods for a single order.
last_updated: Jul 23, 2021
template: concept-topic-template
originalLink: https://documentation.spryker.com/2021080/docs/payments-feature-overview
originalArticleId: db728134-17d6-4023-8d7a-55177ee5af44
redirect_from:
  - /2021080/docs/payments-feature-overview
  - /2021080/docs/en/payments-feature-overview
  - /docs/payments-feature-overview
  - /docs/en/payments-feature-overview
  - /docs/scos/user/features/202200.0/payments-feature-overview.html
---

The *Payments* feature lets your customers pay for orders with none (for example, a [gift card](/docs/pbc/all/gift-cards/gift-cards.html)), one, or multiple payment methods during the checkout process. Most orders are paid with a single payment method, but in some cases, it may be useful to allow multiple payment methods. For example, the customer may want to use two credit cards or a gift card in addition to a traditional payment method.

With different payment gateways, like Amazon Pay, PayPal, and BS Payone, you can adapt to your customers' needs and define the availability of payment methods based on customer preferences and country-specific regulations.

So that your customers can select a payment method during the checkout, you must fulfill the following conditions:
* Make the payment method active.
* Assign the payment method to specific stores.

These settings can be configured in the Back Office.

The Spryker Commerce OS offers integrations with several payment providers that can be used in checkout and order management. You can easily define the availability of a provider based on customer preferences and local regulations and specify the order in which the providers are displayed during checkout.

## Payment providers

The Spryker Commerce OS supports the integration of the following payment providers, which are our official partners:

* [Adyen](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/adyen.html)
* [AfterPay](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/afterpay.html)
* [Amazon Pay](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/amazon-pay.html)
* [Arvato](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/arvato.html)
* [Billie](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/billie.html)
* [Billpay](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/billpay.html)
* [Braintree](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/braintree.html)
* [BS Payone](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/bs-payone/bs-payone.html)
* [Computop](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/computop.html)
* [CrefoPay](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/crefopay.html)
* [Heidelpay](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/heidelpay.html)
* [Klarna](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/klarna.html)
* [Payolution](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/payolution.html)
* [Powerpay](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/powerpay.html)
* [ratenkauf by easyCredit](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/ratenkauf-by-easycredit.html)
* [RatePay](/docs/scos/user/technology-partners/{{page.version}}/payment-partners/ratepay.html)

## Dummy payment

By default, Spryker provides the [DummyPayment](https://github.com/spryker/dummy-payment) module, which has credit card and invoice payments implemented. You can use these implemented payment methods or refer to the DummyPayment module when implementing additional payment methods in your project.
For details about implementing a new payment method, see [how to implement the Direct Debit payment method](/docs/scos/dev/back-end-development/data-manipulation/payment-methods/direct-debit-example-implementation/implementing-direct-debit-payment.html). Based on the examples in these documents, you can implement other payment methods for your projects.

## Payment methods in the Back Office

In the Back Office, you can view all payment methods available in the shop application and make a payment method active (visible) or inactive (invisible) in the **Payment** step of the checkout process. In addition, you can define stores in which a payment method is displayed. If changed, the payment methods are updated in the checkout as well.

{% info_block warningBox "Note" %}

Before managing payment methods in the Back Office, you need to create them by [importing payment methods data using a .CSV file](/docs/scos/dev/data-import/{{page.version}}/data-import-categories/commerce-setup/file-details-payment-method.csv.html).

{% endinfo_block %}

![List of payment methods](https://spryker.s3.eu-central-1.amazonaws.com/docs/Features/Payment/Payment+Methods+Overview/payment-methods-list.png)

To learn more on how to make a payment method available during the checkout and assign it to a different store, see [Edit payment methods](/docs/scos/user/back-office-user-guides/{{page.version}}/administration/payment-methods/edit-payment-methods.html).

<!-- Managing Payment Methods in the Back Office

Overview of the reference information when working with payment methods in the Back Office

HowTo - Import Payment Method Store Relation Data

Hydrating payment methods for an order

  -->

## Related Business User articles

|BACK OFFICE USER GUIDES|
|---|
| [View payment methods](/docs/scos/user/back-office-user-guides/{{page.version}}/administration/payment-methods/view-payment-methods.html)   |
| [Edit payment methods](/docs/scos/user/back-office-user-guides/{{page.version}}/administration/payment-methods/edit-payment-methods.html)   |

{% info_block warningBox "Developer guides" %}

Are you a developer? See [Payments feature walkthrough](/docs/scos/dev/feature-walkthroughs/{{page.version}}/payments-feature-walkthrough.html) for developers.

{% endinfo_block %}
