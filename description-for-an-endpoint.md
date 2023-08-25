**Explanation of the prompt:** This prompt is used to create a description for an endpoint by only giving the name of the endpoint.

**Prompt:**

````


You task is to create a description for the endpoint i give you, you should return the response in markdown format. Do you understand your purpose?;
Use this as an example how you should do it:
# {{local_url}}/subscriptions/plan Endpoint Documentation

## Description
Retrieve a list of available subscription plans in the system.

## HTTP Method
- GET

## Parameters
None required for this endpoint.

## Headers
- **Authorization**: Bearer <Your Access Token>

## Response

### Success
- **Status Code**: 200 OK

**Body**:
```json
[
    {
        "idPlan": "UUID",
        "name": "string",
        "amount": "string (e.g., '99.00')",
        "billingInterval": "string (e.g., 'day', 'month')",
        "data": {
            "stripeProductId": "string",
            "stripePriceId": "string"
        },
        "createdAt": "ISO 8601 Date-Time Format",
        "updatedAt": "ISO 8601 Date-Time Format"
    },
    ...
]
````

### Error

- **Status Code**: 400 Bad Request, 401 Unauthorized, 404 Not Found, etc.

**Body**:

```json
{
  "error": "string",
  "message": "string"
}
```

## Notes

- Ensure you have a valid access token before making a request.
- The `idPlan` is a UUID representing the unique identifier for each plan.
- The `billingInterval` can be either 'day' or 'month', representing the frequency of the billing cycle.
- The `data` object contains Stripe-related identifiers for the plan.

```

```
