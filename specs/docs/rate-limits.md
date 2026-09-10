# Rate limits

Squarespace Commerce APIs employ a rate limit of 300 requests per minute,
an equivalent bandwidth of five requests per second.
Requests over the rate limit receive a `429 Too Many Requests` response
with a cool down period of one minute.

In addition, the [Create Order](/commerce-apis/rate-limits) endpoint has a separate, stricter rate limit of 100 requests **per hour, per website** when an API Key is used for authentication. For clarity, this stricter rate limit **does not** apply when OAuth is used for authentication.

Contact [Customer Care](https://support.squarespace.com/hc/requests/new)
regarding rate limiting or if further assistance is needed while implementing APIs.
