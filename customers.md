# Customers

With Craft Commerce, a _Customer_ is a model representing a person who may place an order.

That person could’ve placed an order as a guest or have an associated Craft [user account](https://docs.craftcms.com/v3/users.html) for logging in and making orders with saved information.

Every Craft user has a customer record by default, even if that user has never created an order.

::: tip
The 1:1 user-to-customer relationship is new to Craft Commerce 3. A migration from Commerce 2 will create a new customer record for any existing Craft user that doesn’t already have one.
:::

Commerce will consolidate customers by email address on order completion.

If a customer checks out as a guest, a new customer record will be created. If a customer record already exists with the same email address, the order will be associated with that existing customer record and the now-orphaned one will be automatically garbage collected. If the guest customer’s email address matches one on a Craft user account, the order will be associated with that user (via the user's customer record) and appear in the user’s order history.

If a customer is logged in, any order will naturally be associated with that user the moment the cart is created and on through completion.

Customers can be found in the control panel by navigating to Commerce → Customers.

## Customer List

The customer list is a paginated data set of all customers in the system linked to a user or having completed orders. The customer list can be searched by name, email, address, and order reference/number.

Customers having user accounts will appear with a link to the respective Craft user in the listing table.

Choose any customer’s email address to see more information.

## Customer

The customer view will show you important information about the customer. The information contained on this page is the same data that is shown on the [customer info tab](#user-customer-info-tab).

### Addresses

The addresses for a customer can be reached via the customer view. Select any address to edit it.

## User Customer Info Tab

A “Customer Info” tab will be available on every user’s account page in the control panel.

This tab contains the following information:

- **Orders**: list of previous orders for the customer.
- **Active Carts**: list of the customer’s active carts based on the [Commerce::\$activeCartDuration](configuration.md#activecartduration) setting.
- **Inactive Carts**: list of the customer’s inactive carts based on the [Commerce::\$activeCartDuration](configuration.md#activecartduration) setting.
- **Addresses**: list of the customer’s addresses, which can be edited and deleted.
- **Subscriptions**: list of the customer's subscriptions.

The visibility of this tab can be controlled with the [Commerce::\$showCustomerInfoTab](configuration.md#showcustomerinfotab) setting. The tab is shown by default.
