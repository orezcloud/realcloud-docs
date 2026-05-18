
<!-- @orez/changelog-entry -->

## v5.0.0 – 2026-05-19

### Major Release – RealCloud ERP v5.0.0

Welcome to RealCloud v5.0.0! This is a major release with substantial new capabilities, stronger financial data integrity, and a noticeably faster, cleaner user experience throughout the platform.

#### New Features

**Batch & Serial Inventory Tracking**

Track physical stock down to the manufacturing lot or individual serial number.

* **Lot & Serial Registration**: Attach manufacturing batch codes and expiry dates; split checkout lines across multiple lot pools.
* **Built-in Safeguards**: Prevents selling items before inbound receipt; credit note returns restricted to actual purchased units.

**Global Search (Ctrl+K / ⌘K)**

Find almost anything from one search palette.

* **Everyday lookup**: Search products, customers, vendors, reports, and quick actions.
* **Document search**: Start query with '>' to search live commerce documents (invoices, bills, etc.).

**Void & Deletion Archive**

Deleted or voided transactions are preserved in a permanent archive with full historical data snapshots and audit trails.

**Advanced Report Generator**

A new generation of interactive reports built for large histories.

* **Full Report Interaction**: Load entire result sets with infinite scroll; sort, group, and customize columns.
* **Drilldowns & Sharing**: Click through to source documents; carry over filters to related reports; bookmark/share via URL.
* **Future-Ready**: Pivot-style analysis coming soon; matrix layouts already supported.

**Real-Time AR & AP Balances**

Customer and vendor outstanding balances update in real time for instant listings and statements at any scale.

**Automated Profit Matrix Report**

New monthly profit-and-loss matrix report that builds itself automatically, aggregating sales, returns, expenses, and margins.

**Dashboard Redesign**

Rebuilt from the ground up for a comprehensive view of business performance.

* **At-a-glance KPIs**: Revenue, expenses, receivables, and financial health ratios with trends.
* **Trend Breakdowns**: Interactive charts, expense breakdowns by account, and top customer insights.
* **Stay Current**: Recent transactions list with payment status; flexible date filters; privacy mode.

**Fast Autocomplete Pickers**

Instant, highlight-matching autocomplete for customers, vendors, and accounts. Includes inline customer creation during checkout.

**Redesigned Quick Actions Menu**

Spacious four-column panel (Add Records, Sales, Purchasing, Money & Stock) with a borderless, clutter-free layout.

#### Improvements

* **Simplified Payment Statuses**: Clear 'PAID' or 'UNPAID' color-coded indicators.
* **Flexible Overpayments**: Allocate payments across calendar dates; record overpayments and split receipts freely.
* **Product-First Grid Rules**: Quantity, rate, and tax fields locked until item selection to guide entry.
* **Isolated Journal Aging**: Receivables and payables shown separately from manual journals in aging statements.

#### Accounting Changes

* **System Account Identity System**: DB-enforced 'SystemAccountRole' for critical accounts (AR, AP, Tax, COGS).
* **Automated Cheque Settlement**: Cheques marked 'Cleared' automatically upon bank deposit.
* **Immutable Tracking Rules**: Product tracking type (Standard, Batch, Serial) is locked after save.
* **Base Unit Restriction**: Tracked products restricted to base unit of measure for clean stock audits.

#### Fixes

* **Clean Deletions**: Deleting parent transactions removes all linked payments and related records.
* **Navigation Links**: Clicking transaction references in reports/lists opens the document.
* **Audit Logs**: Newly created invoices now generate proper edit history records.
* **Form Stability**: Input fields reliably keep focus in modals and overlays.
* **Overlay Reliability**: Dropdowns and modals stay open during interaction with nearby controls.

<!-- @orez/changelog-entry -->

## v4.35.4 – 2026-04-07

* Fixed issue where past payments could not be allocated to future invoices
* Added support for converting grouped report permissions into individual report-level permissions

<!-- @orez/changelog-entry -->

## v4.35.3 – 2026-03-31

* Fixed several permission-related issues

<!-- @orez/changelog-entry -->

## v4.35.1 – 2026-03-31

* Improved automatic conversion from legacy permissions to the new permission system
* Fixed permission-related issues
* Fixed issues with customer/vendor bulk upload

<!-- @orez/changelog-entry -->

## v4.35.0 – 2026-03-31

### Major Feature Update – Advanced Permission System

This release introduces a completely redesigned permission system with significantly improved control and security.

#### Key Features

**Granular Permission Model**

* Replaced simple permission strings with a scope-based action matrix
* 25+ permission scopes covering all business domains:

  * Sales, Purchase, Inventory, Accounting, Cheques, Masters, Reports, Settings
* 6 standard actions per scope:

  * VIEW, CREATE, EDIT, VOID, DELETE, PRINT

**Backdate Controls (Per Document Type)**

You can configure backdate rules separately for each document type (scope), giving you precise control over how far users can work with past data.

* **Maximum Backdate Days**
  Limits how many days back a user can create new documents.

* **Edit Age Limit**
  Restricts how old a document can be for editing after it has been created.

**Special Permissions**

* System-level capability controls:

  * Pricing: under-cost pricing, discount limits, cost visibility
  * Inventory: negative stock, count finalization
  * Advanced operations: locked period edits, approval bypass, multi-store access
* Flexible JSON-based configuration for custom rules

**Store-Level Access Control)**

* Multi-store support with user-to-store mapping
* Restrict access per store
* Option to bypass store restrictions via special permissions

#### Improvements

* **Scalability**: Add new scopes/actions without schema changes
* **Auditability**: Clear permission matrix for compliance reporting
* **Flexibility**: Custom business rules via JSON-based permissions
* **Multi-tenancy**: Store-level access for enterprise use

> Note: Legacy permission remains functional during the transition period. Further refinements will be made based on user feedback.

#### Other Updates

* Restricted one user to a single tenant/account for improved stability
* Added `noOfItems` and `noOfPcs` columns to the main sales report
* Combined product bulk upload and bulk update into a single workflow

  * Download existing data and update via a single Excel file
* Added bulk upload support for customers and vendors (including opening balances)
* Strengthened Chart of Accounts:

  * Reserved names are now non-editable
* Fixed high processing usage in report tables

<!-- @orez/changelog-entry -->

## v4.34.0 – 2026-03-27

* Improved date range selector:

  * Easier selection of month, day, and year
  * Reintroduced year selection

* Added layout configuration for most reports:

  * Customize visible columns
  * Access additional hidden columns
  * Rearrange column order
  * Available via the gear icon near export

<!-- @orez/changelog-entry -->

## v4.33.0 – 2026-03-26

* Improved responsiveness in customer and vendor areas

* General stability improvements

* Added cheque amount configuration:

  * Configure how post-dated cheque (PDC) amounts are calculated
  * Option to include:

    * Only cheques in hand
    * All pending cheques (including transferred cheques to vendors)

<!-- @orez/changelog-entry -->

## v4.32.0 – 2026-03-26

### Document Render Settings

* Introduced customizable document rendering using Handlebars templates
* Enables custom print formats across different sections:

  * Invoice payments
  * Customer-related prints
* API access available within templates
* Supports multiple print templates

**Example Use Cases**

* Customer outstanding reports
* Customer aging reports

> Currently, invoice payment printing is supported.

### Bulk Payment Improvements

* Bulk payments are now tracked as a single entity:

  * System records which payments belong to a bulk transaction

* Added print support for bulk invoice payments:

  * Print a single receipt for multiple payments (e.g., multiple cheques)
  * Fully customizable via document render settings

* Fixed cheque-related issues in bulk payments

<!-- @orez/changelog-entry -->

## v4.31.0 – 2026-03-20

* Added image link settings:

  * Generate multiple image links as needed

* Added new **Monthly Sales Report**

* Introduced custom HTML print support using Handlebars templates

* Added ability to:

  * Activate/deactivate print templates for commerce documents
  * Select a primary print button

<!-- @orez/changelog-entry -->

## v4.30.2 – 2026-03-19

* General stability improvements and bug fixes
* Fixed issue where journals could not be opened from customer inquiry history

<!-- @orez/changelog-entry -->

## v4.30.0 – 2026-03-18

* Added support for invoice payments via journal entries

* Introduced new party auto-allocation method (`/AutoAllocation`)

* Added support for contra settlements:

  * Bill-to-bill
  * Invoice-to-invoice

* Added option to manually resolve bill payments

---
