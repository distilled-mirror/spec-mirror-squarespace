# Making requests to Commerce APIs

In three steps, you can send a successful request to any Commerce API
to manage numerous commerce features of any Squarespace merchant site.

[**Discounts**](/commerce-apis/discounts-overview):
Manage discounts for a site, including their eligibility criteria, discount amount, and activation trigger.

[**Contacts**](/commerce-apis/contacts-overview):
Manage the people associated with a site — customers, subscribers, donors — including their address books and marketing preferences.

[**Analytics**](/commerce-apis/analytics-overview):
Retrieve aggregated commerce data (order counts, totals, donations) for contacts in bulk.

[**Inventory**](/commerce-apis/inventory-overview):
Read and adjust stock information for product variants.

[**Orders**](/commerce-apis/orders-overview):
Access order history for one-time purchases and
subscription orders or import orders from third-party
sales channels.

[**Products**](/commerce-apis/products-overview): Manage physical products, including their variants and images.

[**Profiles**](/commerce-apis/profiles-overview): Read customers, mailing list subscribers,
and donors. Now in maintenance mode — new integrations should use the [Contacts API](/commerce-apis/contacts-overview).

[**Transactions**](/commerce-apis/transactions-overview):
Access financial transactions for orders and donations.

[**Webhook Subscriptions API**](/commerce-apis/webhook-subscriptions-overview):
Subscribe to notifications from a site, like when an order was created, by configuring a webhook endpoint.

## 1. Generate an API key or start the OAuth process

If you don't have an API key or are a registered OAuth client already,
read the [Authentication and permissions](/commerce-apis/authentication-and-permissions) guide.

## 2. Format your request headers

For a successful request, every Commerce API request must use the headers and URL format shown below.
The current version number for each API is located on the API's overview page.
To learn more about versioning, read the [Versioning](/commerce-apis/versioning) guide.

> _Caution: All requests sent over HTTP instead of HTTPS are rejected._

```bash
curl "https://api.squarespace.com/{api-version}/{resource-path}" \
  -H "Authorization: Bearer YOUR_API_KEY_OR_OAUTH_TOKEN" \
  -H "User-Agent: YOUR_CUSTOM_APP_DESCRIPTION" \

  // Add a Content-Type header when making requests with a body.
  -H "Content-Type: application/json"
```

### Recommendations

**Accept header: it's okay to use one, but not necessary**  
Although an `Accept` header is conventional in HTTPS requests,
it's not necessary as Commerce APIs support JSON responses only.

**User-Agent header: it's okay to use default values for testing, but not recommended**  
Default values for `User-Agent` are often injected by HTTP client applications (e.g.`"User-Agent: curl/7.54.0"`).
Although they're okay to use, doing so may be subject to stricter [rate limiting](/commerce-apis/rate-limits).
Requests without a `User-Agent` header are rejected.

## 3. Start making requests

Read the endpoint documentation for any APIs you want to use and then start to make requests!
But, ensure all requests abide by Squarespace [rate limits](/commerce-apis/rate-limits).

All APIs responses are formatted in JSON and use standard status and error codes.
Response codes are listed for every endpoint.

## Next steps

* Learn how Commerce APIs handle [responses and errors](/commerce-apis/responses-error-handling)
* Read the [FAQ](/commerce-apis/faq) for answers to common questions
* Read our [brand guidelines](https://www.squarespace.com/brand-guidelines)
