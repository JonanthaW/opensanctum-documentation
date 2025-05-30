# OpenSanctum API - Getting Started

Welcome to the OpenSanctum API! This guide will help you quickly start using the API to access information about churches and religions around the world.

## Base URL

```https://www.opensanctum.com/v1``` 

---
# Authentication

OpenSanctum uses a state token-based authentication system. There are two main types of access:

- **Public access** – endpoints like `/religion/{id}` and `/churches/{id}` are open to everyone.
- **Protected access** – all other routes require Basic Auth credentials and a valid JWT.

### Register & Login

Users can only register through the official OpenSanctum website. After email verification, a default role is assigned.

**Login endpoint**:
```http
POST /user/basic-auth
Authorization: Basic <base64encoded-credentials>
```

To authenticate using Basic Auth, encode your username and password in the format username:password using Base64, and pass it in the Authorization header. For example:
```
Authorization: Basic dXNlckBleGFtcGxlLmNvbTpteVNlY3JldFBhc3N3b3Jk
```
Tip: In Postman, you can use the Basic Auth tab to automatically generate the header by entering your username and password.


**Response YOUR_API_KEY:**
```json
"eyJhbGciOiJIUzI1NiIsInR5cCI6..."
```
---

### Troubleshooting

- **401 Unauthorized** – Your JWT might be expired or malformed.
- **403 Forbidden** – You are authenticated but do not have the required role.
- **Missing Token** – Make sure you're passing `Authorization: Bearer <your-token>` in the header.
- **CORS Errors** – Make sure your requests originate from allowed domains and are using the correct headers.

For more help, contact support or check the website's FAQ.


---
## Endpoints

### Churches

- `GET /v1/churches/id/{id}`  
  Get church details by its unique ID (Public).

- `GET /v1/churches/name/{name}?page=0`  
  Search churches by name (Requires Basic Auth, paginated).

- `GET /v1/churches/country/{country}?page=0`  
  List churches by country (Requires Basic Auth, paginated).

- `GET /v1/churches/state/{state}?page=0`  
  List churches by state (Requires Basic Auth, paginated).

- `POST /v1/churches/create`  
  Create a new church submission (Requires Basic Auth with roles USER-VERIFIED, SANCTUM or FAITHFUL).
   
  Example (JSON):  
  ```json
  {
    "name": "Church Name",
    "address": "Street Address",
    "postcode": "Postal Code",
    "city": "City",
    "country": "Country",
    "state": "State",
    "latitude": 12.3456,
    "longitude": 65.4321,
    "religion": "Religion Name",
    "denomination": "Denomination",
    "running": true or false,
    "trivia": "Interesting facts or history"
  }
  ```

---
### Religion

- `GET /v1/religion/id/{id}`  
  Get religion details by ID (Public).

- `GET /v1/religion/name/{name}`  
  Search religion by name (Requires Basic Auth).

  Example (JSON):  
```
{
  "id": 1,
  "name": "Christianity",
  "language": "Various",
  "founder": "Jesus Christ",
  "classification": "Monotheistic",
  "description": "A monotheistic religion based on the life and teachings of Jesus Christ.",
  "theology": "Trinitarian",
  "scripture": "Bible",
  "region": "Worldwide",
  "image_url": "https://example.com/images/christianity.png",
  "added_at": "2023-04-15T12:34:56Z"
}

```

---
## Pagination

- Most list endpoints support pagination via the `page` query parameter (default `0`).
- Each page returns up to 5 results.
- Example: `/v1/churches/name/saint?page=2`

---
## Error Handling

- `404 Not Found`  
  Returned when a resource is not found or query parameters are missing/invalid.

- `401 Unauthorized`  
  Returned when Basic Authentication is missing or invalid.

- `403 Forbidden`  
  Returned when the authenticated user lacks permissions.

- `400 Bad Request`  
  Returned on invalid input data.

---
## Troubleshooting

### Common Issues and Solutions

**1. Getting 401 Unauthorized Errors**

- Ensure you include the correct Basic Authentication header for all protected endpoints.
- Verify your username and password are correct.
- Make sure you are not calling protected endpoints without authentication.

**2. Receiving 404 Not Found**

- Double-check the resource ID or name in the request URL.
- Confirm the requested church or religion exists in the database.
- Verify spelling and capitalization (search is case-insensitive but names must be accurate).

**3. 403 Forbidden when creating a church**

- Only authenticated users with roles `ROLE_USER-VERIFIED`, `ROLE_SANCTUM`, `ROLE_FAITHFUL` can submit new churches.
- Verify your user role and permissions.

**4. Empty or Missing Response**

- Check if you included pagination parameters when required.
- If the requested page has no results, try a different page number.
- Confirm your query parameters are not empty or null.

**5. Error 400 Bad Request**

- Ensure all required fields in POST requests are filled and valid.
- Validate JSON syntax and field types.
- Check for invalid characters or malformed input.

---
### Debugging Tips

- Use tools like Postman or curl to test endpoints independently.
- Check API response headers and messages for clues.
- Enable verbose logging on your client HTTP library to inspect request and response data.

---
### Roles

The OpenSanctum API uses a role-based access control system. Here’s what you need to know about how roles work:


#### Available Roles

- **ROLE_USER** (default) – Assigned automatically when a user registers through the website.
- **ROLE_USER-VERIFIED**  – Assigned automatically after the user successfully verifies their email address.  
- **ROLE_SANCTUM** – Reserved for users who actively contribute to the platform, such as reporting critical bugs, providing valuable feedback or purchased via a small monthly subscription. Grants access to additional benefits and features.  
- **ROLE_FAITHFUL** – Available through a future small monthly subscription. This role will come with exclusive features and additional usage benefits.  
- **ROLE_ADMIN** – Internal role for OpenSanctum maintainers only.

#### How to Get a Role

| Role         | How to Obtain                                               |
|--------------|-------------------------------------------------------------|
| `ROLE_USER`  | Automatically assigned upon registration on the website.    |
| `ROLE_USER-VERIFIED`  | Automatically assigned upon verifying your email after registering.    |
| `ROLE_SANCTUM` | Granted as a reward for significant contributions.        |
| `ROLE_FAITHFUL` | Earned via a small subscription (coming soon).          |

#### Checking Your Role

> At this time, the only way to check your current role is by logging into your [OpenSanctum profile](https://www.opensanctum.org/user/profile) on the website. Role information is not yet available via the public API.


---
## Contact and Support

If issues persist, please contact us:

Email: Contato@opensanctum.com  
Website: https://www.opensanctum.com  

---
Thank you for using OpenSanctum API!
