
---

## v4.35.4 – 2026-04-07

* Fixed issue where past payments could not be allocated to future invoices
* Added support for converting grouped report permissions into individual report-level permissions

---

## v4.35.3 – 2026-03-31

* Fixed several permission-related issues

---

## v4.35.1 – 2026-03-31

* Improved automatic conversion from legacy permissions to the new permission system
* Fixed permission-related issues
* Fixed issues with customer/vendor bulk upload

---

## v4.35.0 – 2026-03-31

### 🚀 Major Feature Update – Advanced Permission System

This release introduces a completely redesigned permission system with significantly improved control and security.

#### Key Features

**Granular Permission Model**

* Replaced simple permission strings with a scope-based action matrix
* 25+ permission scopes covering all business domains:

  * Sales, Purchase, Inventory, Accounting, Cheques, Masters, Reports, Settings
* 6 standard actions per scope:

  * VIEW, CREATE, EDIT, VOID, DELETE, PRINT

**Per-Scope Backdate Controls**

* Fine-grained control over document date restrictions
* Configure:

  * Maximum backdate days
  * Edit age limits per scope
* Role-level overrides supported

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

---

## v4.34.0 – 2026-03-27

* Improved date range selector:

  * Easier selection of month, day, and year
  * Reintroduced year selection

* Added layout configuration for most reports:

  * Customize visible columns
  * Access additional hidden columns
  * Rearrange column order
  * Available via the gear icon near export

---

## v4.33.0 – 2026-03-26

* Improved responsiveness in customer and vendor areas

* General stability improvements

* Added cheque amount configuration:

  * Configure how post-dated cheque (PDC) amounts are calculated
  * Option to include:

    * Only cheques in hand
    * All pending cheques (including transferred cheques to vendors)

---

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

---

## v4.31.0 – 2026-03-20

* Added image link settings:

  * Generate multiple image links as needed

* Added new **Monthly Sales Report**

* Introduced custom HTML print support using Handlebars templates

* Added ability to:

  * Activate/deactivate print templates for commerce documents
  * Select a primary print button

---

## v4.30.2 – 2026-03-19

* General stability improvements and bug fixes
* Fixed issue where journals could not be opened from customer inquiry history

---

## v4.30.0 – 2026-03-18

* Added support for invoice payments via journal entries

* Introduced new party auto-allocation method (`/AutoAllocation`)

* Added support for contra settlements:

  * Bill-to-bill
  * Invoice-to-invoice

* Added option to manually resolve bill payments

---
