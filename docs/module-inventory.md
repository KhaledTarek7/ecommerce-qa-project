# Module Inventory

## Purpose

The purpose of the Module Inventory is to identify the main functional areas of the SauceDemo application that will be included in the QA project.

Each module will later be connected to requirements, test scenarios, test cases, test execution results, defects, and automated tests.

## Application Modules

| Module ID | Module                          | Description                                                                                                                 | Initial Risk |
| --------- | ------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ------------ |
| MOD-01    | Authentication / Login          | Handles user authentication, credential validation, login errors, and access to the application.                            | High         |
| MOD-02    | Product Listing & Sorting       | Displays available products and allows users to review product information, add or remove items, and sort the product list. | Medium-High  |
| MOD-03    | Product Details                 | Allows users to open an individual product and view detailed product information.                                           | Medium       |
| MOD-04    | Shopping Cart                   | Displays selected products and allows users to review or remove products before checkout.                                   | High         |
| MOD-05    | Checkout — Customer Information | Collects the customer information required before proceeding with checkout.                                                 | High         |
| MOD-06    | Checkout — Order Overview       | Displays the selected products, pricing information, totals, and final order review before completion.                      | High         |
| MOD-07    | Order Completion                | Confirms that the checkout process has been successfully completed.                                                         | High         |
| MOD-08    | Navigation, Menu & Session      | Handles application navigation, menu options, application state, and user logout.                                           | Medium-High  |

## Functional Flow

The primary application flow is:

`MOD-01 Authentication`

→ `MOD-02 Product Listing`

→ `MOD-03 Product Details` *(optional)*

→ `MOD-04 Shopping Cart`

→ `MOD-05 Checkout — Customer Information`

→ `MOD-06 Checkout — Order Overview`

→ `MOD-07 Order Completion`

→ `MOD-08 Logout`

## Scope Corrections

During initial application analysis, some functionality commonly found in e-commerce applications was identified as unavailable in SauceDemo.

### Registration

User registration will not be included as a module because SauceDemo uses predefined test accounts and does not provide a customer registration workflow.

### Product Search

Product search will not be included as a module because the application does not provide a search feature.

Product **sorting** is available and is therefore included under `MOD-02 Product Listing & Sorting`.

### Payment Processing

A separate payment module will not be created because SauceDemo does not process real customer payments or integrate with a real payment gateway.

The checkout workflow will instead be tested through the available customer-information, order-overview, and order-completion stages.

## Cross-Module Behaviors

Some behaviors affect multiple modules and will be considered during test design rather than treated as independent modules.

These include:

* Cart item-count consistency
* Navigation behavior
* Session behavior
* Validation and error messages
* Application state
* Browser navigation
* UI consistency
* Different predefined user personas

## Risk Classification

Initial risk levels are based on the potential impact of failure on the primary customer journey.

**High-risk functionality** includes authentication, cart operations, checkout, and order completion because defects in these areas can prevent the user from completing the main business workflow.

**Medium-risk functionality** includes product browsing and general navigation because failures may reduce usability or functionality without always preventing the entire purchase flow.

These risk levels are preliminary and may be refined during requirement analysis and test planning.

## Traceability Convention

Stable identifiers will be used throughout the project.

Example:

* Module: `MOD-01`
* Requirement: `REQ-LOGIN-001`
* Test Scenario: `TS-LOGIN-001`
* Test Case: `TC-LOGIN-001`
* Defect: Jira-generated defect ID
* Automated Test: mapped to the corresponding manual test case where applicable

This naming convention will support the Requirements Traceability Matrix and help maintain relationships between requirements, test coverage, execution results, defects, and automation.

