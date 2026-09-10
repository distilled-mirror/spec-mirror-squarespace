# Authentication and permissions

To keep Squarespace merchant site data private and secure,
every request to Commerce APIs must be authenticated and have _minimum_ permissions.
However, authenticated requests automatically have access to public site data,
such as site name, identifier, language, currency, time zone, and location.

Read the permission levels for each Commerce API below.
Then, depending on your development needs,
authenticate requests by using an API key or OAuth access token.

> _Remember: Requests only have access to data for
the website that owns the API key or OAuth access token._

## API permission levels

**Forms API**

* **Read Only**: View form submission data; for Zapier integration only

**Inventory API**

* **Read Only**: View inventory stock levels  
* **Read and Write**: Manage inventory stock levels  

**Orders API**

* **Read Only**: View order, fulfillment, and customer information (name, email, address, and more)  
* **Read and Write**: View customer information (name, email, address, and more); manage order and fulfillment information  

**Products API**

* **Read Only**: View product information, including information for any images and variants; view Store Page information  
* **Read and Write**: Manage product information, including information for any images and variants; view Store Page information  

**Contacts API**

* **Read Only**: View contact records, address books, and marketing preferences
* **Read and Write**: Manage contact records, address books, and marketing preferences

**Discounts API**

* **Read Only**: View discount records
* **Read and Write**: Manage discount records

**Webhook Subscriptions API** *(OAuth only)*

* **Read and Write**: Create, update, delete, and test webhook subscriptions

**Profiles API** *(maintenance mode — new integrations should use the [Contacts API](/commerce-apis/contacts-overview))*

* **Read Only**: View the name, address, email, marketing preferences, and other profile information of customers, subscribers, and other website users  

**Transactions API**

* **Read Only**: View transactional order, donation data, and customer information (email)  

## Authenticating requests

Depending on your development needs,
you can use a generated API key or start the OAuth process with Squarespace
to become a registered OAuth client. A Squarespace merchant site can use both
API keys and OAuth for data access, but Squarespace Extensions are required to use OAuth.

### Custom applications

With [Squarespace's Commerce Advanced](https://www.squarespace.com/pricing) plan,
you can develop a custom application for a Squarespace merchant site.

Follow the steps below to generate an API key for a custom application.

1. Log in to a Squarespace site.
1. In the left nav, click **Settings**; scroll down and click **Advanced**.
1. Click **Developer API Keys**.
1. Click the **GENERATE KEY** button.
1. In the dialog, add a key name under "KEY NAME",
and select one or more Commerce APIs under "PERMISSIONS" and permission level.
1. Record the generated key in a safe and secure place.

For security reasons, this is the only time the API key is visible.
API keys will never expire as long as the merchant site remains active.

### Commercial development

Squarespace Extensions allow customers on any plan
to optimize and expand their site in a few clicks.
If you'd like to develop a new Extension,
start the OAuth client process [here](https://account.squarespace.com/developer-apps).
Once you've obtained OAuth credentials, you can use our [OAuth 2.0 Guide](/oauth) to learn how to authorize your application to integrate with Squarespace and use Squarespace APIs.

## Next steps

* [Make requests to Commerce APIs](/commerce-apis/making-requests)
* Read the [FAQ](/commerce-apis/faq) for answers to common questions
* Read our [brand guidelines](https://www.squarespace.com/brand-guidelines)
