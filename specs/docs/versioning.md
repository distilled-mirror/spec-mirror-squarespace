# Versioning

Each Commerce API resource has an independent version number, where the current version number is listed in the resource's overview page. Versions are specified in request URIs per the following format:

**Format**

```html
https://api.squarespace.com/{api-version}/{resource-path}
```

**Examples**

```html
https://api.squarespace.com/v1/contacts
https://api.squarespace.com/v2/commerce/products
https://api.squarespace.com/1.0/commerce/orders
```

## Versioning methodology and breaking changes

Our versioning methodology has evolved over time to provide more stability and less overhead for developers.

### Pre-2025 (1.0 and 1.1)

Squarespace endpoints released before 2025 used a Semantic Versioning format (`Major.Minor`), where minor updates sometimes introduced breaking changes.

### 2025 onwards

Starting in 2025, Squarespace uses a non-SemVer approach, using integers: v1, v2, v3, etc. Non-breaking changes are added to the existing version without incrementing the version string. A version increment is only triggered by a breaking change that requires developers to update their code.

The following types of changes will not result in a version increment. Any code that interacts with the Squarespace APIs must be able to handle the following types of changes:

* **Additive response contents:** New fields or objects in a JSON response.
* **Relaxed constraints:** Making a required field optional, or loosening of validation rules (e.g. a string with a maximum length of 50 is expanded to 100).
* **New HTTP methods:** Allowing new HTTP methods for endpoints that previously did not support them.
* **New query parameters:** Adding optional query parameters to existing endpoints (e.g. new filter or sort options).
* **Bug fixes:** Bug fixes that do not result in breaking changes.

All changes are, nonetheless, registered in our [changelog](/commerce-apis/changelog), even if they do not require a version bump.

### Current versioning per resource path

| Resource path | Latest version | Legacy versions |
| :--- | :--- | :--- |
| `/products` | `v2` | `1.1`, `1.0` |
| `/contacts` | `v1` | `N/A` |
| `/discounts` | `v1` | `N/A` |
| `/inventory` | `1.0` | `N/A` |
| `/orders` | `1.0` | `N/A` |
| `/profiles` | `1.0` | `N/A` |
| `/transactions` | `1.0` | `N/A` |
| `/webhook_subscriptions` | `1.0` | `N/A` |

## Legacy API versions

Squarespace supports legacy API versions for an extended period. We provide significant advance notice before deprecating any version. Supported legacy versions will be documented per API, including the information you need to upgrade your applications.
