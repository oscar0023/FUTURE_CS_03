# API Security Risk Analysis - JSONPlaceholder

This repository contains the deliverables for a security risk analysis conducted on the **JSONPlaceholder** API. The goal of this project was to identify potential security vulnerabilities based on the OWASP API Security Top 10 and propose actionable remediations.

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Tools Used](#tools-used)
- [Scope](#scope)
- [Methodology](#methodology)
- [Identified Risks](#identified-risks)
- [Deliverables](#deliverables)
- [How to Use This Repository](#how-to-use-this-repository)
- [Author](#author)

---

## Project Overview

**Target:** [JSONPlaceholder](https://jsonplaceholder.typicode.com/) (a free fake API for testing and prototyping)  
**Date:** March 2026  
**Author:** Oscar Alotchewou ALIDJINOU

The assessment followed a black-box approach using Postman to simulate real-world attacks and evaluate the API's security posture.

---

## Tools Used

- **Postman** – For sending HTTP requests and analyzing responses
- **GitHub** – For version control and documentation hosting
- **PDF** – For the final report

---

## Scope

The analysis focused on the following endpoints and operations:

- `GET /posts`, `/comments`, `/users` – Data retrieval
- `POST /posts` – Resource creation
- `PUT /posts/{id}` – Resource update
- `DELETE /posts/{id}` – Resource deletion
- `GET /users/{id}` – Access to specific user data

Administrative-like functions (e.g., `DELETE /users/1`) were also tested for authorization flaws.

---

## Methodology

The assessment followed a structured 4-step methodology:

### 1. Reconnaissance
Manual exploration of the API using Postman to map all available endpoints, request methods, and parameters.

### 2. Threat Modeling
Identification of relevant threats from the OWASP API Security Top 10 list (2023).

### 3. Testing
- **Authentication Testing:** Attempted to access protected endpoints without credentials.
- **Authorization Testing:** Attempted to access admin functions using a low-privilege user.
- **Resource Consumption Testing:** Sent large payloads and repeated requests to test rate limiting.

### 4. Documentation
All successful exploits were captured via screenshots and included in the final report.

---

## Identified Risks

| Risk ID | Name | Severity | Description |
|--------|------|----------|-------------|
| API1:2023 | Broken Object Level Authorization | HIGH | Unauthorized access to other users' data via ID manipulation |
| API2:2023 | Broken Authentication | CRITICAL | No login mechanism; all endpoints accessible without identity verification |
| API4:2023 | Unrestricted Resource Consumption | HIGH | No rate limiting or payload size restrictions |
| API5:2023 | Broken Function Level Authorization | CRITICAL | Standard users can access admin-level functions |

*For full details, please refer to the [full report](./report/API_Security_Risk_Analysis.pdf).*

---

## Deliverables

This repository includes:

- 📄 `task3.pdf` – The complete security report
- 📸 `/screenshots` – Postman requests and responses demonstrating each vulnerability
- 📘 `README.md` – This file, explaining the project

---

## Author

**Oscar Alotchewou ALIDJINOU**  
📧 oscaralidjinou27@gmail.com

---

## 📌 Disclaimer

This project was conducted for **educational and testing purposes only** on a publicly available fake API. The vulnerabilities identified are inherent to the design of JSONPlaceholder (which is intentionally insecure for learning). Do not attempt to test APIs without proper authorization.

---
