# Pharmacy-340B

**Property of St. Luke's Health System – Internal Use Only**

Pharmacy-340B is a secure web application developed for St. Luke’s Health System to streamline drug classification, 340B pricing compliance, and pharmaceutical purchasing. It replaces manual spreadsheet workflows and integrates directly with SQL Server for robust backend processing.

![image](https://github.com/user-attachments/assets/b663237f-6631-417f-9602-8e45f5b9387e)

---

## 📑 Table of Contents

- [Key Features and Functionality](#-key-features-and-functionality)
- [Architecture and Tech Stack](#️-architecture-and-tech-stack)
- [Deployed URLs](#-deployed-urls)
- [Development Setup](#️-development-setup)
- [Available Commands](#-available-commands)
- [Testing](#-testing)
- [Deployment](#-deployment)
- [Branching Strategy](#-branching-strategy)
- [Additional Resources](#-additional-resources)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## 📌 Key Features and Functionality

- 🔍 Manage National Drug Codes (NDCs), pricing, and classifications
- 🧾 Map external data sources into internal structures
- 📊 Generate financial and compliance reports
- 🗃️ Maintain reference/master data (GL categories, pharmacy types)
- 🧠 Role-based access control via Microsoft Azure AD
- 💼 Business logic handled through SQL stored procedures

---

## ⚙️ Architecture and Tech Stack

| Layer         | Technology                                                                 |
|--------------|------------------------------------------------------------------------------|
| Frontend     | [React](https://reactjs.org), [TypeScript](https://www.typescriptlang.org), [React Router](https://reactrouter.com), [React-Bootstrap](https://react-bootstrap.github.io), [ag-Grid](https://www.ag-grid.com)
| Backend      | [Remix](https://remix.run), [Node.js](https://nodejs.org), [MSSQL (Node)](https://www.npmjs.com/package/mssql), [SQL Server](https://www.microsoft.com/en-us/sql-server) |
| Authentication | [Azure Active Directory](https://learn.microsoft.com/en-us/azure/active-directory/) |


---

## 🌍 Deployed URLs

| Environment | URL                                      |
|-------------|-------------------------------------------|
| 🧪 Dev       | https://pharmacy-340b-dev.azurewebsites.net       |
| 🧫 Test   | https://pharmacy-340b-test.azurewebsites.net     |
| ✅ Prod      | https://pharmacy340b.slhs.org             |

---

## 🛠️ Development Setup

```bash
# Clone the repository
git clone git@github.com:St-Lukes-Health-System/pharmacy-340b.git

# Navigate into the repo
cd pharmacy-340b

# Checkout dev branch
git checkout dev

# Install dependencies
npm install

# (Optional) Generate Prisma client
npx prisma generate

# Start development server
npm run dev
```

---

## 🚀 Available Commands

| Command             | Description                                |
|---------------------|--------------------------------------------|
| `npm run dev`        | Start local dev server                     |
| `npm run build`      | Build production bundle                    |
| `npm run start`      | Start built production server              |
| `npm run test`       | Run all unit tests                         |
| `npm run lint`       | Lint all files                             |
| `npm run lint:fix`   | Auto-fix linting issues                    |
| `npm run format`     | Format code using Prettier                 |

---

## 🧪 Testing

- Unit testing via [Vitest](https://vitest.dev) or [Jest](https://jestjs.io)
- Example:  
  ```bash
  npm run test
  ```
- Coverage reports and e2e automation integration pending

---

## 📦 Deployment

- Managed via SLHS internal CI/CD pipelines
- Push to `main` triggers production deployment
- Push to `dev` triggers staging deployment
- All secrets and configurations handled via secure vault

---

## 🌿 Branching Strategy

| Branch       | Purpose                      |
|--------------|------------------------------|
| `main`       | Production-ready code        |
| `dev`        | Development integration      |
| `feature/*`  | New features and enhancements|
| `hotfix/*`   | Emergency production patches |

---

## 📚 Additional Resources

- [Confluence: Pharmacy-340B Documentation](https://confluence.slhs.org/pharmacy-340b)
- [Azure AD Integration Guide](https://learn.microsoft.com/en-us/azure/active-directory/)
- [Remix Deployment Reference](https://remix.run/docs/en/main/pages/deployment)
- [ag-Grid React Guide](https://www.ag-grid.com/react-data-grid/)

---

## 🤝 Contributing

Only authorized developers from St. Luke’s may contribute.  
Please ensure all PRs follow these conventions:

- Use consistent commit formats (e.g., Conventional Commits)
- All forms and routes must be validated with Zod
- Ensure test coverage before requesting review
- Provide clear change logs and references to tickets/issues

---

## 🔒 License

This project is proprietary software owned by **St. Luke’s Health System**.  
All rights reserved. Unauthorized use or distribution is strictly prohibited.

---

## 📞 Contact

- Gary Beers: beersg@slhs.org
- Justin Hall: halljus@slhs.org
- Justin Hamilton: hamiltju@slhs.org
