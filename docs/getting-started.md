# Getting Started with OpenSanctum API

Welcome to the OpenSanctum API! This guide will help you quickly understand how to access and use our free and public endpoints to explore data about churches, religions, and sacred places worldwide.

---

## Base URL

All API requests start with the base URL:

```
https://www.opensanctum.com/v1/
```

---

## Example Requests

### Get Church by ID

Retrieve detailed information about a church by its unique ID.

```bash
curl https://www.opensanctum.com/v1/churches/id/1
```

### Get Religion by ID

Retrieve information about a religion by its unique ID.

```bash
curl https://www.opensanctum.com/v1/religion/id/1
```

---

## Response Format

All responses are returned in JSON format.

Example response for a church:

```json
{
  "id": 1,
  "name": "St. Patrick's Cathedral",
  "address": "5th Ave, New York, NY",
  "religion": "Christianity",
  "denomination": "Catholic",
  "status": "Active",
  "description": "Historic cathedral in NYC."
}
```

---

## Using the API

- Public endpoints do **not require authentication**.
- For authenticated endpoints, see the [Authentication guide](authentication.md).
- Use HTTPS for all requests to ensure data security.

---

## Rate Limits

There are currently **no rate limits** on public endpoints.

---

## Next Steps

- Check out the [Endpoints documentation](endpoints/) for detailed info on all available API routes.
- Learn about [authentication](authentication.md) if you want to access restricted features.

---

If you have questions or need help, please open an issue on our GitHub or contact support@opensanctum.com.

Happy exploring!
