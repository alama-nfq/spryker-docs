---
title: Creating returns
description: Learn how to create returns in the Back Office
template: back-office-user-guide-template
related:
  - title: Viewing returns of an order
    link: docs/scos/user/back-office-user-guides/page.version/sales/orders/viewing-returns-of-an-order.html
  - title: Changing the state of order items in returns
    link: docs/pbc/all/return-management/page.version/manage-in-the-back-office/change-the-state-of-order-items-in-returns.html
---

This document describes how to create returns in the Back Office.

If a sales order item is [returnable](/docs/pbc/all/return-management/{{page.version}}/return-management.html), you can create a return for it. On the Storefront, only registered users can create returns. In the Back Office, you can create returns for both the registered and guest users.

## Prerequisites

You can create returns for the items that are in **Exported** or **Delivered** states only. To learn how to change item states, see [Changing the state of order items](/docs/scos/user/back-office-user-guides/{{page.version}}/sales/orders/changing-the-state-of-order-items.html).

To start managing orders, go to **Sales&nbsp;<span aria-label="and then">></span> Orders**.

## Creating returns

1. On the **Orders** page, next to the order you want to return, click **View**.
2. On the **Order Overview** page, click **Return**.
3. On the **Create Return** page, select the items that are to be returned.

{% info_block warningBox "Returning bundles" %}

You can only return separate items in a [configurable bundle](/docs/scos/user/features/{{page.version}}/configurable-bundle-feature-overview.html), not the bundle itself.

You can return [product bundles](/docs/scos/user/features/{{page.version}}/product-bundles-feature-overview.html) only as a single item.

{% endinfo_block %}

4. Optional: For **Select reason**, select a reason for returning the items.
5. Click **Create return**.
    This creates the return and opens the **Return Overview** page.

### Reference information: Creating returns

This section describes the attributes you see when creating a return.

| ATTRIBUTE | DESCRIPTION |
|-|-|
| Order reference | Unique identifier of the order for which you are creating a return. Click to go to the order's page where you can view and edit it. |
| Fulfilled by merchant | Name of the merchant the item belongs to. Click to go to merchant's page where you can view and edit their information. |
| Merchant Order Reference | Unique identifier of the merchant order. |
| Product | All the items in the order. For returning, you can only select the items that are in **Exported** or **Delivered** state. To learn how to change item states, see [Changing the state of order items](/docs/scos/user/back-office-user-guides/{{page.version}}/sales/orders/changing-the-state-of-order-items.html). |
| Quantity | Product quantity in the order. |
| Price | Product price in the order. |
| Total | Total amount paid for the item. |
| Return policy | Return policy an item is controlled by. |
| State | Order state of an item. |
