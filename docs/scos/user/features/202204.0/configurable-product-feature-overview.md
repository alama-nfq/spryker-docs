---
title: Configurable Product feature overview
description: All the details about the Configurable Product feature of Spryker.
last_updated: Nov 29, 2022
template: concept-topic-template
redirect_from:
  - /docs/scos/user/features/201903.0/configurable-product-feature-overview.html
  - /docs/scos/user/features/201907.0/configurable-product-feature-overview.html
---

The *Configurable Product* feature introduces a new type of product, a configurable product, that customers can customize.

The feature lets you sell complex products with modular designs or services. For example, if you sell clothes, your customers can define the material and color and add their names to the product. Or if you are selling a service, you can allow them to select a preferred date and time for the service delivery.

## Configurable product

A *configurable product* is a product that customers can customize based on the parameters provided in a [product configurator](#product-configurator).

For example, if you are selling a workstation installation service, before purchasing it, customers can select a preferred date and time of installation.

### Configuring a configurable product

To configure a product, a customer opens a product configurator from the *Product Details* page by clicking the **Configure** button. They are then redirected back to the *Product Details* page and can add the configured product to the wishlist or cart.

![configure-button-on-product-details-page](https://spryker.s3.eu-central-1.amazonaws.com/docs/Features/Product+Management/Configurable+Product/Configurable+Product+feature+overview/configure-button-on-product-details-page.png)

After adding a configurable product to the cart, a customer can change the product configuration from the **Cart** page.

![configure-button-on-the-cart-page](https://spryker.s3.eu-central-1.amazonaws.com/docs/Features/Product+Management/Configurable+Product/Configurable+Product+feature+overview/configure-button-on-the-cart-page.png)

### Creating configurable products

Configurable products are created in two steps:

1. A Back Office user creates regular products, or a developer imports them. See [Creating an abstract product](/docs/scos/user/back-office-user-guides/{{page.version}}/catalog/products/manage-abstract-products-and-product-bundles/create-abstract-products-and-product-bundles.html) to learn how products are created in the Back Office or [File details: product_concrete.csv](/docs/scos/dev/data-import/{{page.version}}/data-import-categories/catalog-setup/products/file-details-product-concrete.csv.html) to learn about how developers import the file.
2. A developer converts regular products into configurable products by importing configuration parameters. To learn about the file they import, see [File details: product_concrete_pre_configuration.csv](/docs/scos/dev/data-import/{{page.version}}/data-import-categories/special-product-types/configurable-product-import-category/file-details-product-concrete-pre-configuration.csv.html).

### Managing configurable products

A Back Office user can add configurable products as regular products to pages, categories, and content items.

They can see which products are configurable in the product catalog and edit them as regular products. However, a Back Office user cannot change configuration parameters.

![configurable-product-entry-in-the-back-office](https://spryker.s3.eu-central-1.amazonaws.com/docs/Features/Product+Management/Configurable+Product/Configurable+Product+feature+overview/configurable-product-entry-in-the-back-office.png)

In the orders, a Back Office user can see which products are configurable. They can also see the configuration of each product, but they cannot change the selected parameters.

![order-with-a-configurable-product](https://spryker.s3.eu-central-1.amazonaws.com/docs/Features/Product+Management/Configurable+Product/Configurable+Product+feature+overview/order-with-a-configurable-product.png)

## Product configurator

A *product configurator* is a tool that allows customers to customize the product parameters provided by the shop owner or product manufacturer.

You can create a product configurator as a part of your shop or integrate a third-party one. The feature is shipped with an example product configurator. The example product configurator allows configuring the *Date* and *Preferred time of the day* parameters.

![examplary-product-configurator](https://spryker.s3.eu-central-1.amazonaws.com/docs/Features/Product+Management/Configurable+Product/Configurable+Product+feature+overview/examplary-product-configurator.png)

### How a Spryker shop interacts with a product configurator

A Spryker shop interacts with product configurators using parameters. When a customer is redirected from a Spryker shop to the configurator page, the shop passes the customer and product parameters. When the customer is redirected back to the shop, the configurator passes the updated parameters back.

The behavior of the configurator is based on the parameters passed by a shop. For example, a shop passes the `store_name` parameter. If a customer is redirected from a US store, the language of the configurator is English. Also, the shop passes the URL of the page the customer is redirected from. After the customer saves the configuration, the configurator uses this URL to redirect them back to the same page.

The selected configuration is also passed back to the shop as parameters. The shop uses the parameters to display the selected configuration on all related pages and process the order with the product.

### Parameter types

There are two parameter types: configuration parameters and display parameters.

*Configuration parameters* are used by shops to interact with product configurators.

*Display parameters* are used to display product configuration on the Storefront and in the Back Office.

Display parameter values are usually converted from configuration parameter values to show data in a user-friendly format. For example, a product configurator passes the configuration parameter to a shop: `"time_of_the_day": 3`. Since, in the configurator, `3` stands for `afternoon`, the shop displays **Preferred time of the day: Afternoon**.

![display-data-in-a-configurator](https://spryker.s3.eu-central-1.amazonaws.com/docs/Features/Product+Management/Configurable+Product/Configurable+Product+feature+overview/display-data-in-a-configurator.png)


### Availability calculation in a product configurator

The availability of a configurable product is based on the selected configuration.

A customer selects the quantity of a product in a configurator or a shop. If a configurator allows them to select a product quantity, it passes the specified quantity to the shop as a parameter. Otherwise, it passes the availability as a parameter, and they select the product quantity in the shop.

If a configurator does not pass availability, [regular product availability](/docs/marketplace/user/features/{{page.version}}/marketplace-inventory-management-feature-overview.html) is used.

### Price calculation in a product configurator

The price of a configurable product is based on the selected configuration. When a customer chooses a configuration, the product's price in the selected configuration is displayed. After they save the configuration, the product price in the selected configuration is passed to the shop. The customer is redirected back to the shop where they can purchase the product for the price.

If the configurator does not provide a price, [a regular product price](/docs/pbc/all/price-management/prices-feature-overview/prices-feature-overview.html) is used.

### Complete and incomplete configuration

When [importing configurable products](/docs/scos/dev/data-import/{{page.version}}/data-import-categories/special-product-types/configurable-product-import-category/file-details-product-concrete-pre-configuration.csv.html), a developer defines if the configuration is complete for each product.

If the configuration is complete, on the *Product details* page, a customer sees a message that the configuration is complete. By default, the message is followed by the first three descriptive attributes set in the configurator. Under the attributes, the **Show** and **Hide** buttons allow the customer to expand and collapse the remaining attributes to review them. The customer can purchase the product without again opening the configurator and selecting parameters, if they determine the configuration is complete.

![configurtion-complete-message](https://spryker.s3.eu-central-1.amazonaws.com/docs/scos/user/Features/Configurable+Product+feature+overview/configurtion-complete-message.png)

If the configuration is not complete, on the *Product details* page, a customer sees a message that the configuration needs to be completed. To purchase the product, they open the configurator and select a configuration. However, they can add a product with an incomplete configuration to a wishlist. In this scenario, they can finish the configuration from the *Wishlist* page.

![incomplete-configurtion-message](https://spryker.s3.eu-central-1.amazonaws.com/docs/Features/Product+Management/Configurable+Product/Configurable+Product+feature+overview/incomplete-configurtion-message.png)


Even if all the parameter values are [preconfigured](#preconfigured-parameter-values), but the configuration is not complete, a customer has to open the configurator and save the configuration. They are not required to change the preconfigured values, though.

![configuration-is-not-complete-message-with-preconfigured-parameters](https://spryker.s3.eu-central-1.amazonaws.com/docs/Features/Product+Management/Configurable+Product/Configurable+Product+feature+overview/configuration-is-not-complete-message-with-pre-configured-parameters.png)

#### Request for Quote with a configurable product

The information in [Complete and incomplete configuration](#complete-and-incomplete-configuration) applies to [Quotation Process & RFQ](/docs/scos/user/features/{{page.version}}/quotation-process-feature-overview.html) functionalities. A customer can only request a quote for a product with a complete configuration.

#### Shopping List with a configurable product

The information in [Complete and incomplete configuration](#complete-and-incomplete-configuration) applies to the [Shopping List](/docs/pbc/all/shopping-list-and-wishlist/shopping-lists-feature-overview/shopping-lists-feature-overview.html) functionality. A customer can add products with the complete or incomplete configuration.

#### Wish List with a configurable product

The information in [Complete and incomplete configuration](#complete-and-incomplete-configuration) applies to the [Wish List](/docs/pbc/all/shopping-list-and-wishlist/wishlist-feature-overview.html) functionality. A customer can add products with the complete or incomplete configuration.

### Preconfigured parameter values

When a developer creates configurable products by importing them, they can preconfigure parameter values. If customers choose to configure such a product, they start with the preconfigured parameter values and can change them.

If a developer also defines that the configuration of such a product is complete, a customer sees the preconfigured parameter values on the *Product details* page. They can add the product to the cart without adjusting the configuration.

If a developer defines that the configuration of such a product needs to be completed, on the *Product details* page a customer does not see the preconfigured parameter values. However, they are still assigned to the product. The customer has to configure the product, but they can keep the same preconfigured parameter values.

## Configurable product on the Storefront

Customers configure a product on the Storefront as follows:

![configurable-product-on-the-storefront](https://spryker.s3.eu-central-1.amazonaws.com/docs/Features/Product+Management/Configurable+Product/Configurable+Product+feature+overview/configurable-product-on-the-storefront.gif)

{% info_block warningBox "Developer guides" %}

Are you a developer? See [Configurable Product feature walkthrough](/docs/scos/dev/feature-walkthroughs/{{page.version}}/configurable-product-feature-walkthrough/configurable-product-feature-walkthrough.html) for developers.

{% endinfo_block %}
