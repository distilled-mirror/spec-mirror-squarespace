# Responses and error handling

Commerce APIs always return a response body in JSON.
Ordering of the response data is not guaranteed to be in a specific order unless explicitly stated on the API reference page.

All documented fields are always present in a response body, even if the field's value is `null`.
Array fields that contain no data can either be represented as a `null` value or an empty array (`[]`).
Please make sure you can handle either possibility.

## Error objects

All response errors include a standard error object.
Each field is always present, but values may be `null` as indicated.

```javascript
{
  // General purpose descriptor for the type of the error.
  // The possible values are documented for each endpoint.
  "type": "INVALID_REQUEST_ERROR",

  // A descriptor for the subtype of the error, when available.
  // The possible values are documented for each endpoint.
  // This field is nullable.
  "subtype": "MISSING_ARGUMENT",

  // A plain English message intended for developers for debugging purposes.
  // This value should not be displayed to an end-user.
  "message": "An expiration date is required.",

  // Machine-readable data for generating user-friendly error messages;
  // intended for developers and users alike.
  // Reserved for future use; always `null` at this time.
  "details": { ... },

  // Provides an identifier for reporting issues to Squarespace Customer Care.
  // Use the form below to report any occurrences of `5xx` range
  // errors, and please be sure to reference this id.
  // Form: https://support.squarespace.com/hc/requests/new#choose-topic
  "contextId": "RUPSUSPOW"
}
```

## Status codes and error conditions

In general, Commerce APIs use standard HTTP response codes as listed below.
Though each endpoint also supports additional statuses,
consult endpoint documentation for further details.

### 2xx: Successful requests

`200 OK` The request was processed successfully and any expected data is present in the response body.

`201 Created` A new resource was created and is present in the response body.

`202 Accepted` The request was received, is being processed, and any expected data is present in the response body.

`204 No Content` The request was processed successfully and no data is present in the response body.

### 4xx: Client errors

Codes in the `4xx` range indicate that something is wrong with your request
or that your request cannot be completed due to a conflicting state that can
be avoided through further action.
The information you receive in the response provides some level of detail to help you debug the issue.

`400 Bad Request` The request failed due to one or more causes of a bad query parameter,
malformed body, or the body referencing an unknown system resource.

`401 Unauthorized` The request failed due to unexpected authorization header information,
which may be caused by a missing header or that the provided token was invalid or expired.

`402 Payment Required` The request failed because the website that owns the authorization token is expired.

`403 Forbidden` The request failed because the provided token does not have sufficient permissions.

`404 Not Found` The requested resource could not be found.

`405 Method Not Allowed` The request attempted to access a resource using an unsupported HTTP method.

`409 Conflict` The request could not be processed due to the state of the server at the time of the request.
This can be due to a variety of circumstances, such as concurrent requests competing for the same resource,
a system configuration option prevents the request from being processed, or other state-specific causes.
Depending on the cause, conflicts may be resolved by waiting for resources to become available or by updating
the state of the system to enable the original request to succeed.

`429 Too Many Requests` The application has issued too many requests and may be able to issue new requests
after a cool down period. Refer to the [rate limiting](/commerce-apis/rate-limits)
guidelines for more information.

### 5xx: Server errors

Any errors in the `5xx` range indicate a problem happened with Squarespace's servers.
Please [report](https://support.squarespace.com/hc/requests/new#choose-topic)
the issue and include the `contextId` you received in the response.


_Note: 5xx errors are sometimes caused by transient network faults meaning that a subsequent request will succeed when retried after a delay. For this reason, we recommend implementing a retry strategy using [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff) and halting execution after an appropriate number of attempts._
