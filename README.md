# Project Prompt: Distributor and Shop Management System

## 1. Project Overview

Build a complete, responsive, full-stack web application called **Distributor & Shop Management System**. The platform will connect product distributors with retail shops. Distributors can list products, manage their inventory, receive orders from shops, and maintain accounting records. Shops can browse products, place orders with distributors, manage their own stock, and maintain their own accounting records.

The system must have separate registration, login, dashboards, permissions, inventory, and accounting features for distributors and shops.

## 2. User Roles and Authentication

Create two independent user roles:

### A. Distributor
- Register and log in through a dedicated distributor registration/login page.
- Create and manage a distributor business profile.
- Add, edit, delete, and publish products.
- Set product name, category, SKU, description, unit, purchase price, selling price, available quantity, and product image.
- View incoming shop orders and manage their statuses.
- Calculate stock, purchases, sales, and remaining inventory.
- Create and manage journals, ledgers, trial balances, and balance sheets.
- View sales reports, purchase reports, profit/loss reports, and outstanding payments.

### B. Shop
- Register and log in through a dedicated shop registration/login page.
- Create and manage a shop profile.
- Browse available products from registered distributors.
- Search and filter products by name, category, distributor, and price.
- View product details and available stock.
- Add products to a cart and place orders.
- Track order status and view order history.
- Calculate and manage shop inventory.
- Record purchases, sales, expenses, and payments.
- Create and manage journals, ledgers, trial balances, and balance sheets.
- View sales reports, purchase reports, profit/loss reports, and outstanding payments.

Each role must have a separate dashboard and role-based permissions. Shops must not access distributor-only pages, and distributors must not access shop-only pages.

## 3. Main Website Pages

Create the following pages:

1. Home page with a professional introduction and buttons for Distributor Login, Distributor Registration, Shop Login, and Shop Registration.
2. Distributor registration and login.
3. Shop registration and login.
4. Distributor dashboard.
5. Shop dashboard.
6. Product marketplace.
7. Product details page.
8. Shopping cart and checkout.
9. Order management.
10. Distributor inventory management.
11. Shop inventory management.
12. Accounting dashboard.
13. Journal entries.
14. Ledger accounts.
15. Trial balance.
16. Balance sheet.
17. Income statement and profit/loss report.
18. Sales and purchase reports.
19. User profile and business settings.

## 4. Inventory and Stock Management

Implement an accurate inventory management system for both distributors and shops.

Required features:
- Add, update, and remove products.
- Track opening stock, purchases, sales, returns, damaged goods, and closing stock.
- Automatically update stock when a purchase or sale is completed.
- Display low-stock alerts and out-of-stock warnings.
- Maintain a stock movement history.
- Search, sort, filter, and paginate inventory.
- Calculate inventory valuation using a consistent valuation method, such as weighted-average cost.
- Prevent orders that exceed available stock.
- Record stock adjustments with reasons and timestamps.

Use this formula:

**Closing Stock = Opening Stock + Stock In − Stock Out ± Adjustments**

Keep distributor inventory and shop inventory separate. When a distributor fulfills a shop's order, reduce the distributor's stock and increase the shop's stock only when the configured fulfillment/receipt process confirms the transfer. Prevent duplicate stock updates.

## 5. Order Management System

Create a complete ordering workflow between distributors and shops.

1. A distributor publishes products with prices and available quantities.
2. A shop browses the marketplace and selects a distributor's products.
3. The shop adds products to its cart and submits an order.
4. The distributor receives the order notification.
5. The distributor accepts, rejects, or prepares the order.
6. The distributor updates the status to dispatched.
7. The shop confirms receipt of the products.
8. The system updates inventory and records the relevant accounting transactions.
9. Both users can view order details, invoices, payment status, and order history.

Support these order statuses: Pending, Accepted, Rejected, Processing, Dispatched, Delivered, and Cancelled.

Include order numbers, timestamps, quantities, unit prices, discounts, taxes when applicable, delivery charges, and totals.

## 6. Accounting and Bookkeeping Module

Both distributors and shops must have independent accounting systems. Each business must only access its own financial records.

### A. General Journal
- Record transactions using double-entry bookkeeping.
- Include transaction date, reference number, description, debit account, credit account, and amount.
- Validate that total debits equal total credits for every journal entry.
- Support manual entries and automatically generated entries from confirmed purchases, sales, expenses, returns, and payments.
- Provide edit controls with audit history and safe correction/reversal procedures.

### B. Ledger
- Create individual ledger accounts.
- Display opening balance, debit, credit, running balance, and closing balance.
- Filter transactions by account and date range.
- Link each ledger transaction to its journal entry.

### C. Trial Balance
- Generate a trial balance for a selected date or period.
- Display account name, debit balance, and credit balance.
- Verify that total debit balances equal total credit balances.
- Clearly report discrepancies instead of silently balancing incorrect records.

### D. Balance Sheet
Generate a balance sheet automatically from posted accounting records.

Use the accounting equation:

**Assets = Liabilities + Owner's Equity**

Include:
- Current assets: cash, bank, inventory, and accounts receivable.
- Non-current assets where applicable.
- Current liabilities: accounts payable and other short-term liabilities.
- Long-term liabilities where applicable.
- Owner's capital and retained earnings.

The balance sheet must show the selected reporting date and must reconcile with the accounting ledger.

### E. Income Statement
Include:
- Sales revenue.
- Sales returns and discounts.
- Net sales.
- Cost of goods sold.
- Gross profit.
- Operating expenses.
- Other income and expenses.
- Net profit or loss.

### F. Financial Reports
- Daily, weekly, monthly, and yearly reports.
- Cash and bank book.
- Accounts receivable and accounts payable.
- Customer and supplier statements.
- Printable reports and PDF exports.
- CSV or Excel exports where appropriate.

Accounting must follow double-entry principles. Do not calculate financial statements merely by adding sales and expenses without considering inventory, liabilities, capital, receivables, and payables.

## 7. Dashboard Design

### Distributor Dashboard
Display:
- Total products.
- Available stock value.
- Low-stock products.
- Total shop orders.
- Pending orders.
- Completed sales.
- Outstanding receivables.
- Monthly revenue and profit charts.
- Recent transactions.

### Shop Dashboard
Display:
- Total products in stock.
- Current inventory value.
- Low-stock products.
- Recent purchases.
- Total sales.
- Outstanding payables.
- Monthly sales and expense charts.
- Recent orders and transactions.

Use clear cards, charts, data tables, status badges, date filters, and quick-action buttons.

## 8. Recommended Technology Stack

Use the following stack unless a better technical choice is justified:

- **Frontend:** React.js with Vite.
- **Styling:** Tailwind CSS.
- **Backend:** Java with Spring Boot REST APIs.
- **Database:** MySQL.
- **Authentication:** Spring Security with secure session-based authentication or JWT.
- **ORM:** Spring Data JPA and Hibernate.
- **Charts:** Recharts.
- **PDF reports:** A suitable Java PDF library.
- **API testing:** Postman.
- **Version control:** Git and GitHub.

Use a clean, modular architecture with separate frontend, backend, and database layers.

## 9. Database Design

Design a normalized relational database with appropriate primary keys, foreign keys, indexes, unique constraints, and timestamps.

Include tables or equivalent entities for:

- users
- roles
- distributor_profiles
- shop_profiles
- products
- product_categories
- inventory
- stock_movements
- carts
- cart_items
- orders
- order_items
- payments
- accounts
- journal_entries
- journal_entry_lines
- ledger transactions or ledger views
- expenses
- sales
- purchases
- returns
- audit_logs

A product listing must identify its distributor. Inventory records must be associated with the correct business. Accounting entries must be associated with the business that owns them.

Avoid duplicate records and maintain referential integrity. Use database transactions for order fulfillment, stock updates, and accounting posting.

## 10. Security and Validation

- Secure password hashing.
- Role-based authorization on the backend, not just hidden frontend buttons.
- Validate all inputs on both frontend and backend.
- Prevent SQL injection and unauthorized data access.
- Protect against cross-business data leakage.
- Prevent duplicate order submissions and duplicate accounting postings.
- Use database transactions for critical operations.
- Keep audit logs for important stock, order, and accounting changes.
- Never store plain-text passwords or expose secrets in source code.
- Use environment variables for database credentials and other secrets.

## 11. User Interface and Experience

Create a modern, professional business management interface suitable for small and medium-sized businesses.

Design requirements:
- Responsive layout for desktop, tablet, and mobile.
- Professional sidebar navigation and top navigation bar.
- Separate visual identity for distributor and shop dashboards.
- Consistent typography, spacing, colors, forms, and tables.
- Clear loading, success, empty, and error states.
- Confirmation dialogs for destructive actions.
- Search, filtering, pagination, and sorting.
- Accessible labels and keyboard-friendly controls.

The website should be easy to use for people with basic computer skills.

## 12. Development Requirements

Build the application in working stages:

**Stage 1:** Define requirements, architecture, database schema, and project structure.

**Stage 2:** Create the database and implement registration, login, authentication, and authorization.

**Stage 3:** Build distributor and shop dashboards and business profiles.

**Stage 4:** Implement product listings, inventory management, stock calculations, and stock movement history.

**Stage 5:** Implement cart, order placement, distributor order processing, delivery confirmation, and payment tracking.

**Stage 6:** Implement double-entry journals, ledgers, trial balances, balance sheets, and income statements.

**Stage 7:** Build dashboards, charts, invoices, and downloadable reports.

**Stage 8:** Add validation, error handling, security, automated tests, and responsive design.

**Stage 9:** Provide setup instructions and deployment guidance.

## 13. Testing and Acceptance Criteria

The project is complete only when:

- Distributor and shop registration/login work independently.
- Users cannot access another business's private data.
- Distributors can publish products and shops can order them.
- Order statuses update correctly.
- Inventory changes accurately when orders are fulfilled and received.
- Stock calculations handle purchases, sales, returns, and adjustments.
- Every posted journal entry has equal debit and credit totals.
- Ledger balances agree with journal entries.
- Trial balances reconcile.
- Balance sheets satisfy Assets = Liabilities + Equity.
- Income statements calculate profit or loss correctly.
- Invalid transactions are rejected with clear error messages.
- Reports can be filtered and exported.
- The application runs using the documented setup instructions.

Write unit tests and integration tests for authentication, inventory calculations, order processing, accounting calculations, and access control.

## 14. Expected Deliverables

Provide:
1. Complete frontend source code.
2. Complete Spring Boot backend source code.
3. Database schema and SQL initialization scripts.
4. REST API documentation.
5. Sample data for testing.
6. Automated tests.
7. A README with installation and execution instructions.
8. An `.env.example` file without real secrets.
9. Instructions for running the project locally in IntelliJ IDEA and VS Code.
10. Deployment instructions.

Do not produce only a static UI or demonstration mockup. Build a functional full-stack application with persistent database storage and working business logic.

Start by presenting the architecture, database relationships, and implementation plan. Then implement the project module by module, providing complete, consistent code and exact file paths. Explain how to run and test each stage before proceeding to the next.
