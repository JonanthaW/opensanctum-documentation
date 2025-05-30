# Authentication

OpenSanctum API supports both **public** and **authenticated** access levels to provide flexible usage options.

---

### Roles & Permissions

OpenSanctum uses a role-based access control system to manage user permissions and features. Here is an overview of what each role entails:

- **ROLE_USER**  
  - Assigned automatically upon user registration on the website.  
  - Allows basic access to the API endpoints that require authentication (beyond public endpoints).  
  - Access to personal profile and settings on the website.

- **ROLE_USER-VERIFIED**  
  - Assigned automatically after the user verifies their email address.
  - Can submit new churches for approval.  
  - Grants full authenticated access to some protected API routes.  
  - Ability to receive notifications and access additional site features reserved for verified users.
  -  Eligible for early access to community events and leaderboard.

- **ROLE_SANCTUM**  
  - Can be earned by reporting verified bugs or purchased via a monthly subscription.  
  - Unlocks premium API access, including higher rate limits and extended data endpoints.  
  - Access to special tools for data contribution and moderation.  
  - Eligible for early access to new features and community events.

- **ROLE_FAITHFUL**  
  - The highest subscription tier, earned through community contributions or purchased.  
  - Full access to all API features and exclusive premium content.  
  - Priority support and direct communication channels with the OpenSanctum team.  
  - Recognition as a key community member with special badges on the website.

> 🔐 **Note:** User roles are assigned and managed only on the website after login. Roles determine access to features both on the API and the website, so make sure to verify your email and consider subscribing for additional benefits.


### API Usage and Rate Limiting

To ensure fair and stable access to the OpenSanctum API, rate limiting is enforced. This protects the API from excessive requests that could degrade service quality for other users.

**Current Rate Limit Configuration:**

- Applies to all API endpoints under `/v1/*`.
- Limits requests based on the client's IP address (`getRemoteAddr()`).
- Each client can make up to **100 requests every 10 minutes**.
- If the limit is exceeded, the client receives an HTTP response with status `429 Too Many Requests` and a JSON message:
  ```json
  {
    "message": "Too many requests, please try again after a few seconds!"
  }
  
This mechanism helps protect OpenSanctum’s infrastructure while providing a smooth experience for all users.


## Infrastructure  

This configuration applies only to public routes at the moment. In the future, rate limits will be adjusted based on subscription levels for private routes, allowing premium roles (e.g., ROLE_SANCTUM, ROLE_FAITHFUL) to enjoy higher or customized limits according to their plans.
