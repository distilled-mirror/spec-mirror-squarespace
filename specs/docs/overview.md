# Overview of Commerce APIs

With Squarespace Commerce APIs, you can build applications to manage the commerce features of a Squarespace merchant site.

**Analytics API:** Retrieve aggregated commerce data (order counts, totals, donations) for contacts in bulk.

**Contacts API:** Manage the people associated with a site — customers, subscribers, donors — including their address books and marketing preferences.

**Discounts API:** Manage discounts for a site, including their eligibility criteria, discount amount, and activation trigger.

**Inventory API:** Read and adjust stock information for product variants.

**Orders API:** Access order history for one-time purchases and subscription
orders or import orders from third-party sales channels.

**Products API:** Manage physical, service, gift card, and download products, including their images and variants (if supported).

**Profiles API:** Read customers, mailing list subscribers, and donors. Now in maintenance mode — new integrations should use the [Contacts API](/commerce-apis/contacts-overview).

**Transactions API:** Access financial transactions for orders and donations.

**Webhook Subscriptions API:** Subscribe to notifications from a site, like when an order was created, by configuring a webhook endpoint.

## Structure and design

All Commerce APIs are built on HTTPS and designed with REST principles in mind.
Every endpoint uses HTTPS features such as authentication, standard verbs,
and standard response status codes.
In addition, APIs that support resource updates via POST allow partial updates.

Authentication for Commerce APIs also provides permissions
to keep Squarespace merchant site data private and secure.

## Next steps

* Become familiar with [commerce terms](/commerce-apis/glossary) and how they're related to the APIs
* Learn how to [send authenticated requests](/commerce-apis/authentication-and-permissions)
* Read the [FAQ](/commerce-apis/faq) for answers to common questions
* Read our [brand guidelines](https://www.squarespace.com/brand-guidelines)
