# Authentication

OpenSanctum API supports both **public** and **authenticated** access levels to provide flexible usage options.

---

## Public Access

Certain API endpoints are **open to everyone** and do **not require authentication**. For example:

- `GET /v1/churches/id/{id}`
- `GET /v1/religion/id/{id}`

These endpoints are free to use and ideal for quick lookups without any API keys or tokens.

---

## Authenticated Access

Some API endpoints require authentication to access enhanced features, contribute data, or access user-specific resources.

### How to Get an API Key

Currently, API keys are issued by the OpenSanctum team upon request. To obtain an API key:

- Visit our website [opensanctum.com](https://www.opensanctum.com)

### Using Your API Key

Include your API key in the HTTP `Authorization` header of each request you want to do.

