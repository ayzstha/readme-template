# readme-template

# Pharmacy-340B Application

## Overview

The Pharmacy-340B Application is a robust web-based solution designed to streamline and manage operations for healthcare organizations participating in the 340B Drug Pricing Program. This program enables eligible entities to acquire outpatient drugs at significantly reduced prices. Our application provides comprehensive tools for National Drug Code (NDC) management, financial categorization, efficient data processing, and compliant reporting, ensuring healthcare organizations can effectively manage their drug procurement and inventory within regulatory frameworks.

## Core Functionality

This application provides critical features to facilitate 340B program management:

* **NDC (National Drug Code) Management:**
    * Comprehensive tracking of drug codes, pricing, and formulary information.
    * Management of drug classifications and categories.
    * Support for integrating and utilizing multiple data sources for drug information.

* **Pharmacy GL Categorization:**
    * Systematic organization of pharmaceutical items by General Ledger (GL) categories.
    * Facilitates accurate financial tracking and reporting.

* **Data Import and Processing:**
    * Robust capabilities for importing data from diverse external sources.
    * Flexible mapping of external data to internal database structures.
    * Support for various file formats and complex data transformations.

* **Reporting:**
    * Generation of essential reports for compliance, auditing, and management purposes.
    * Support for data exports to aid in further analysis.
    * Specialized reporting for areas such as Oral Chemotherapy.

* **Master Data Management:**
    * Centralized maintenance of reference data across the entire application.
    * Management of covered entities, pharmacy categories, and other crucial master data elements.

## Technical Architecture

The Pharmacy-340B Application is built on a modern, secure, and scalable web stack.

### Frontend

* **Framework:** Built with **React** and **TypeScript** for a dynamic and type-safe user interface.
* **Routing:** Utilizes **React Router** for seamless navigation within the single-page application.
* **Data Grids:** Leverages **ag-Grid** for advanced and highly customizable data grid displays, crucial for managing complex pharmaceutical data.
* **UI Components:** Employs **React-Bootstrap** for a consistent and responsive user interface, enhancing development speed and consistency.
* **Notifications:** Integrates **react-hot-toast** for non-intrusive user notifications and feedback.

### Backend

* **Framework:** Powered by **Node.js** with the **Remix** framework, offering a full-stack web development experience with server-side rendering capabilities.
* **Database Interaction:** Direct integration with **SQL Server** using the `mssql` package.
* **Data Access:** Adopts a **stored procedure-based data access pattern** for efficient and secure database operations.
* **Validation:** Implements strong data validation using **Zod** schema validation, ensuring data integrity and security.

### Authentication & Security

* **Identity Provider:** Seamless integration with **Microsoft Azure AD** for robust authentication.
* **Authorization:** Implements **Role-Based Access Control (RBAC)** to manage user permissions.
* **Granular Control:** Supports **employee-level authorization** for fine-grained access management.
* **Session Management:** Utilizes **session-based security** for user authentication and state management.

### Data Flow

1.  **User Interaction:** UI components on the frontend trigger actions or data fetchers (e.g., form submissions, data requests).
2.  **Server-Side Execution:** These actions invoke corresponding server-side functions within the Remix backend.
3.  **Database Interaction:** Server-side functions execute SQL stored procedures to interact with the SQL Server database.
4.  **Data Processing:** Data retrieved from or sent to the database is validated using Zod and transformed as needed.
5.  **UI Update:** The processed results are returned to the frontend, where the UI is updated to display the information.

### Key Design Patterns

* **Server-Side Data Processing:** Emphasis on robust model functions on the server for data manipulation and business logic.
* **Consistent Error Handling and Logging:** Standardized approaches for managing errors and logging application events.
* **Componentized UI:** A highly modular and reusable UI architecture, promoting maintainability and scalability.
* **Form Validation with Schema Enforcement:** Strong validation at various layers to ensure data quality and prevent invalid submissions.

## Project Structure
PHARMACY-340B/
├── .github/
│   └── workflows/
│       └── ci.yml             # GitHub Actions CI/CD workflow
├── .react-router/
│   └── types/                 # React Router type definitions
├── .vscode/
│   ├── extensions.json        # Recommended VS Code extensions
│   └── settings.json          # VS Code workspace settings
├── app/                       # Core application source code
│   ├── assets/
│   │   └── images/            # Static image assets
│   ├── auth/                  # Authentication related modules
│   │   ├── auth.server.ts     # Server-side authentication logic
│   │   ├── session.server.ts  # Session management logic
│   │   └── types.ts           # Authentication related types
│   ├── core/                  # Core application utilities and common modules
│   │   ├── dirty-forms-tracker.tsx # Form state tracking
│   │   ├── env.server.ts      # Server-side environment variables
│   │   ├── errors.tsx         # Custom error components/handling
│   │   ├── logger.server.ts   # Server-side logging utility
│   │   ├── no-access.tsx      # No access page
│   │   ├── no-found.tsx       # Not found page
│   │   ├── sql-config.server.ts # SQL Server connection configuration
│   │   ├── sql-error.tsx      # SQL error handling component
│   │   ├── sql-response-server.ts # SQL response handling
│   │   ├── test-db-connection.server.ts # DB connection testing
│   │   ├── types.ts           # Core types
│   │   ├── utils.test.ts      # Core utilities tests
│   │   └── utils.ts           # Core utilities
│   ├── lib/                   # Reusable UI components and client-side utilities
│   │   ├── ag-grid-status-bar.tsx # ag-Grid custom status bar
│   │   ├── ag-grid-utils.tsx  # ag-Grid specific utilities
│   │   ├── ag-select-cell-editor.tsx # ag-Grid custom cell editor
│   │   ├── client-only-with-fallback.tsx # Client-side only rendering with fallback
│   │   ├── common-options.ts  # Common options/configurations
│   │   ├── field-errors.tsx   # Field error display component
│   │   ├── general-modals.tsx # Reusable modal components
│   │   ├── grid-actions.tsx   # Grid action components
│   │   ├── my-toaster.tsx     # Custom toast notifications
│   │   ├── self-submitting-cell-editor.tsx # Self-submitting ag-Grid cell editor
│   │   ├── spinner.tsx        # Loading spinner component
│   │   ├── stored-proc-utils.server.ts # Server-side stored procedure utilities
│   │   └── utils.ts           # Client-side utilities
│   ├── models/                # Data models and schemas
│   ├── routes/                # Remix routes (server-side and client-side logic per route)
│   │   ├── +future.ts         # Future flag for Remix
│   │   ├── +routes.ts         # Main route definitions
│   │   └── +server-build.d.ts # Server build type definitions
│   ├── styles/                # Stylesheets
│   │   ├── app.css            # Main application CSS
│   │   ├── bootstrap.scss     # Bootstrap custom SCSS
│   │   ├── pivot-reports.css  # Styles for pivot reports
│   │   └── tippy.css          # Styles for Tippy.js tooltips
│   └── validation/            # Data validation schemas and logic
│       ├── entry.client.tsx   # Client-side entry point for hydration
│       ├── entry.server.tsx   # Server-side entry point for SSR
│       ├── menu-items.tsx     # Menu item definitions
│       ├── navigation-link.tsx # Navigation link component
│       └── navigation.tsx     # Navigation component
│       └── root.tsx           # Root layout component
│       └── routes.tsx         # Route configuration
├── build/                     # Compiled application output
├── docs/                      # Project documentation
├── mocks/                     # Mock data for development/testing
├── node_modules/              # Project dependencies
├── playwright/                # Playwright end-to-end tests
├── public/                    # Static assets served directly
├── vitest/                    # Vitest unit/integration tests
├── .dockerignore              # Files to ignore when building Docker image
├── .env.example               # Example environment variables
├── .env                       # Environment variables
├── .eslintrc.js               # ESLint configuration
├── .gitignore                 # Git ignore file
├── .npmrc                     # npm configuration
├── .nvmrc                     # Node Version Manager configuration
├── .prettierignore            # Prettier ignore file
├── Dockerfile                 # Docker build instructions
├── eslint.config.js           # ESLint configuration
├── package-lock.json          # npm dependency lock file
├── package.json               # Project dependencies and scripts
├── playwright.config.ts       # Playwright configuration
├── react-router.ts            # React Router related configurations
├── README.md                  # This README file
├── RELEASING.md               # Release process documentation
├── renovate.json              # Renovate Bot configuration for dependency updates
├── start.sh                   # Startup script
├── TODO.txt                   # Project TODOs
├── tsconfig.json              # TypeScript configuration
└── vite.config.ts             # Vite build tool configuration

## Getting Started

### Prerequisites

* Node.js (LTS version recommended)
* npm (or yarn)
* SQL Server instance
* Azure AD application registration (for authentication)

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-org/pharmacy-340b.git](https://github.com/your-org/pharmacy-340b.git)
    cd pharmacy-340b
    ```
2.  **Install dependencies:**
    ```bash
    npm install
    ```
3.  **Configure Environment Variables:**
    * Create a `.env` file based on `.env.example`.
    * Populate it with your SQL Server connection string, Azure AD details, and other necessary configurations.

4.  **Database Setup:**
    * Ensure your SQL Server is running.
    * You may need to run specific SQL scripts (e.g., for stored procedures, table creation) if provided. *(Placeholder: Instructions for database schema setup)*

### Running the Application

1.  **Start the development server:**
    ```bash
    npm run dev
    ```
2.  **Access the application:**
    Open your browser and navigate to `http://localhost:3000` (or whatever port your Remix app starts on).

## Contributing

* **Fork the repository.**
* **Create a new branch** for your feature or bug fix (`git checkout -b feature/your-feature-name`).
* **Make your changes** and ensure tests pass.
* **Commit your changes** with descriptive commit messages.
* **Push your branch** to your forked repository.
* **Open a Pull Request** to the `main` branch of this repository, describing your changes in detail.

Please refer to our `CONTRIBUTING.md` (if available) for more detailed guidelines.

## Running Tests

* **Unit/Integration Tests (Vitest):**
    ```bash
    npm run test
    ```
* **End-to-End Tests (Playwright):**
    ```bash
    npm run e2e
    ```

## License

This project is licensed under the [Your Chosen License Name] - see the `LICENSE` file for details.
*(Example: MIT License)*

## Contact

For questions or support, please open an issue in the GitHub issue tracker or contact [your-email@example.com].
