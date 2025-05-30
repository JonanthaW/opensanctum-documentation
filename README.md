# OpenSanctum API Documentation

Welcome to the official documentation for the [OpenSanctum](https://www.opensanctum.com) API — your gateway to discovering and contributing to a global directory of churches, temples, mosques, and sacred sites.


## 🔍 Overview

OpenSanctum is an open, community-driven API platform that provides comprehensive, accurate, and up-to-date information about churches, religions, and holy places around the world. Designed with developers and enthusiasts in mind, OpenSanctum offers a rich dataset accessible through a RESTful API built on modern technologies.

The project aims to foster global cultural and religious knowledge sharing by allowing users to contribute new data, verify existing entries, and engage with a vibrant community. OpenSanctum balances ease of access with robust security via token-based authentication, role management, and a subscription model offering enhanced features.

Whether you’re building an app, researching religious sites, or contributing to a worldwide database, OpenSanctum provides a reliable and extensible platform to meet your needs.
No authentication is required for public endpoints, and contributions are welcome!

---

## 📖 Documentation Structure

This repository contains markdown-based documentation structured as follows:

- [`getting-started.md`](docs/getting-started.md) — How to use the API, with quick examples
- [`authentication.md`](docs/authentication.md) — API key usage and permissions
- [`faq.md`](docs/faq.md) — Frequently Asked Questions

---

## Get Started

To begin using the API, visit:

https://www.opensanctum.com/document/api


For example queries and full endpoint descriptions, head to [`docs/getting-started.md`](docs/getting-started.md).


# For Developers

OpenSanctum is designed to be developer-friendly, providing clear, well-documented RESTful endpoints and a modern tech stack to facilitate integration and extension.
Key Features for Developers:

    * REST API with Pagination & Filtering: Access detailed data on churches, religions, and holy places with flexible query parameters and pagination support.

    * Token-Based Authentication: Secure endpoints with JWTs; public endpoints exist for basic data retrieval.

    * Role-Based Access Control: Differentiate users by roles like ROLE_USER, ROLE_SANCTUM, and ROLE_FAITHFUL to control access to features and data.

    * Caching: Uses method-level caching to improve performance for frequent queries.

    * Contribution Workflow: Developers can submit new data through temporary tables that require approval before becoming public.


Getting Started:

    * Use Postman or similar tools to test authentication and API endpoints.

    * Implement your own clients by including the JWT in the Authorization header with Bearer <token>.

    * Review the entity models and service layers to understand the data structures and business logic.

    * Contribute to the project by submitting issues, pull requests, or reporting bugs.

Important Notes:

    * Registration is only available through the official website to maintain data integrity.

    * User roles and permissions are crucial for accessing protected endpoints; always authenticate before calling these.

    * Future plans include adding subscription-based premium roles and enhanced community tools.


## Future Updates & Community Engagement

OpenSanctum is an evolving project with regular updates planned to improve features, expand data coverage, and enhance user experience.
Upcoming Features

    * Subscription Plans: Introduction of premium roles such as ROLE_SANCTUM and ROLE_FAITHFUL with exclusive benefits.

    * Enhanced Data Verification: Improved workflows for user-submitted data approval and moderation.

    * Expanded API Endpoints: More detailed data, including events, histories, and multimedia resources.

    * Community Gamification: Incentives and rewards for contributors helping grow and verify the database.

    * Improved Frontend Features: New tools for browsing, searching, and interacting with the data.

## Stay Connected
Stay up-to-date with the latest news, updates, and community discussions through our social media channels:

- **Twitter:** [@OpenSanctum](https://x.com/OpenSanctum)
- **Reddit:** [r/OpenSanctum](https://reddit.com/r/OpenSanctum)
- **Instagram:** [@OpenSanctum](https://instagram.com/OpenSanctum)


Follow, join the conversation, and help shape the future of OpenSanctum!

## 📬 Contributing

Have suggestions or want to help improve the documentation? Feel free to:

- Open an issue
- Submit a pull request

We're building OpenSanctum in the open — your contributions make it better for everyone.

---

## 📜 License

OpenSanctum is free and open under the [MIT License](LICENSE).
