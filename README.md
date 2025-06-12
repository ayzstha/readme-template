# readme-template

# Pharmacy-340B

**Property of St. Luke's Health System – Internal Use Only**

Pharmacy-340B is a secure, enterprise-grade web application developed for St. Luke’s Health System to support operations under the federal 340B Drug Pricing Program. The application modernizes outdated spreadsheet workflows and provides robust tools for drug data management, reporting, and compliance.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Tech Stack](#tech-stack)
- [Authentication & Security](#authentication--security)
- [Development Setup](#development-setup)
- [Branching Strategy](#branching-strategy)
- [Deployment](#deployment)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Overview

The 340B Drug Pricing Program allows eligible healthcare providers to purchase outpatient drugs at reduced prices. Pharmacy-340B helps manage data and workflows required to maintain program compliance and optimize pharmacy operations.

This application supports:
- Processing and validating external purchase data
- Managing drug codes and pricing
- Classifying pharmacy items for GL reporting
- Generating regulatory and internal reports
- Managing master reference data across entities

---

## Features

- National Drug Code (NDC) tracking and management
- General Ledger (GL) categorization of pharmaceuticals
- Data import and mapping from various formats
- Compliance and operational reporting
- Support for multiple covered entities
- Role-based access control
- Azure Active Directory integration

---

## Architecture

**Frontend**
- Built with React and TypeScript
- UI components using React-Bootstrap
- Data grids powered by ag-Grid
- Client-side validation with Zod
- Navigation via React Router
- Notifications via react-hot-toast

**Backend**
- Node.js + Remix framework
- SQL Server as the data source
- Business logic in stored procedures
- Validation and transformation of all inbound/outbound data

**Data Flow**
1. UI triggers fetchers or form actions
2. Server routes invoke SQL stored procedures
3. Validated results are returned to the frontend
4. UI components update accordingly

---

## Tech Stack

- React
- TypeScript
- Remix (Node.js)
- SQL Server
- Zod (validation)
- React-Bootstrap
- ag-Grid
- Azure Active Directory (AAD)
- npm

---

## Authentication & Security

Authentication is handled via Microsoft Azure Active Directory with silent login as the default, falling back to Microsoft’s login prompt. Access is role-based and session-driven. All protected routes are enforced at the server level.

- AAD Group Mapping must be configured during app registration
- All users must be employees with valid AAD accounts

---

## Development Setup

1. Clone the repository
   ```
   git clone https://github.com/stlukeshealth/pharmacy-340b.git
   ```

2. Install dependencies
   ```
   npm install
   ```

3. Set environment variables
   Create a `.env` file based on `.env.example`.

4. Run the development server
   ```
   npm run dev
   ```

5. Prisma (if applicable)
   ```
   npx prisma generate
   ```

---

## Branching Strategy

- `main`: Production-ready code
- `dev`: Development and staging
- `feature/*`: Feature-specific branches
- `hotfix/*`: Emergency fixes to be merged into `main`

Refer to `RELEASING.md` for the full release workflow.

---

## Deployment

Deployment pipelines are handled via [internal CI/CD tooling] and are triggered on pushes to the `main` branch. Ensure code is merged into `main` via pull requests with passing tests and review.

- Environment variables are managed via a secure vault
- Azure App Service or container-based deployment (depending on environment)

---

## Testing

- Unit testing with Vitest or Jest (TBD)
- Integration tests planned
- Manual QA required before promoting to `main`
- Test coverage reports generated during CI

Run tests locally:
```
npm run test
```

---

## Contributing

Contributions are welcome by team members with access. All changes must be made through pull requests with:
- Clear commit messages
- Linked task/issue references
- Code review by at least one other developer
- Passing CI checks

Style Guide:
- Follow TypeScript best practices
- Enforce schema validation on all input/output
- Keep UI components reusable and modular

---

## License

This project is the property of **St. Luke’s Health System**.  
Unauthorized distribution or use outside of SLHS is prohibited.

---

## Contact

For internal questions or support, please contact:

- Pharmacy-340B Dev Team  
- Email: pharmacy340b-dev@slhs.org  
- Slack: #pharmacy340b-dev  

