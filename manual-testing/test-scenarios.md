# Test Scenarios

## Purpose

This document defines the high-level test scenarios derived from the documented functional requirements.

A test scenario describes **what functionality or behavior should be verified** without defining the detailed execution steps or specific test data.

Detailed test cases will be created separately.

---

# MOD-01 — Authentication / Login

## Scenario Coverage

| Scenario ID  | Related Requirement(s)                      | Test Scenario                                                                                         | Test Type                 | Priority |
| ------------ | ------------------------------------------- | ----------------------------------------------------------------------------------------------------- | ------------------------- | -------- |
| TS-LOGIN-001 | REQ-LOGIN-001, REQ-LOGIN-002                | Verify that an authorized user can authenticate using valid credentials.                              | Positive / Functional     | High     |
| TS-LOGIN-002 | REQ-LOGIN-003, REQ-LOGIN-006                | Verify authentication behavior when an invalid username is provided with an otherwise valid password. | Negative / Functional     | High     |
| TS-LOGIN-003 | REQ-LOGIN-003, REQ-LOGIN-006                | Verify authentication behavior when a valid username is provided with an invalid password.            | Negative / Functional     | High     |
| TS-LOGIN-004 | REQ-LOGIN-003, REQ-LOGIN-006                | Verify authentication behavior when both username and password are invalid.                           | Negative / Functional     | High     |
| TS-LOGIN-005 | REQ-LOGIN-004, REQ-LOGIN-006                | Verify validation when the username is not provided.                                                  | Negative / Validation     | High     |
| TS-LOGIN-006 | REQ-LOGIN-005, REQ-LOGIN-006                | Verify validation when the password is not provided.                                                  | Negative / Validation     | High     |
| TS-LOGIN-007 | REQ-LOGIN-004, REQ-LOGIN-005, REQ-LOGIN-006 | Verify validation when both username and password are not provided.                                   | Negative / Validation     | High     |
| TS-LOGIN-008 | REQ-LOGIN-007                               | Verify that a locked-out user is prevented from accessing the authenticated application.              | Negative / Access Control | High     |

---

## Scenario Design Rationale

The authentication scenarios were designed to cover the main credential partitions and validation conditions.

### Valid Credential Partition

A user provides an authorized username and valid password.

Covered by:

`TS-LOGIN-001`

### Invalid Credential Partitions

Invalid authentication may occur when:

* Username is invalid.
* Password is invalid.
* Both username and password are invalid.

Covered by:

`TS-LOGIN-002`
`TS-LOGIN-003`
`TS-LOGIN-004`

### Missing Required Data

Required authentication information may be incomplete when:

* Username is missing.
* Password is missing.
* Both fields are missing.

Covered by:

`TS-LOGIN-005`
`TS-LOGIN-006`
`TS-LOGIN-007`

### Restricted User State

A user may have otherwise recognized credentials but still be prevented from accessing the application because the account is locked.

Covered by:

`TS-LOGIN-008`

---

## Test Design Techniques

The Login module primarily applies the following test design techniques:

### Equivalence Partitioning

Credential inputs are divided into logical groups such as:

* Valid username
* Invalid username
* Valid password
* Invalid password
* Missing username
* Missing password
* Locked user

Representative test data will later be selected from these partitions.

### Negative Testing

Invalid and incomplete authentication conditions are intentionally tested to verify that unauthorized access is prevented and appropriate validation is provided.

### Error Guessing

Additional login conditions may be explored during manual execution based on QA experience and observed application behavior.

Examples may include unusual characters, whitespace, input formatting, or navigation behavior.

These exploratory ideas will not automatically be treated as formal requirements unless appropriate.

---

## Requirement Coverage

The current Login scenarios provide planned coverage for:

* REQ-LOGIN-001
* REQ-LOGIN-002
* REQ-LOGIN-003
* REQ-LOGIN-004
* REQ-LOGIN-005
* REQ-LOGIN-006
* REQ-LOGIN-007

At this stage, each documented Login requirement is mapped to at least one test scenario.

Detailed test cases will provide the actual test data, execution steps, and expected results.
# MOD-02 — Product Listing & Sorting

## Scenario Coverage

| Scenario ID | Related Requirement(s) | Test Scenario | Test Type | Priority |
|---|---|---|---|---|
| TS-PROD-001 | REQ-PROD-001 | Verify that available products are displayed after successful authentication. | Positive / Functional | High |
| TS-PROD-002 | REQ-PROD-002 | Verify that each product listing provides sufficient identifying product information. | Positive / UI Functional | Medium |
| TS-PROD-003 | REQ-PROD-003, REQ-PROD-005 | Verify that a user can add a product to the cart from the product listing and that the cart indicator is updated. | Positive / Functional | High |
| TS-PROD-004 | REQ-PROD-004, REQ-PROD-005 | Verify that a previously added product can be removed from the product listing and that the cart indicator is updated. | Positive / Functional | High |
| TS-PROD-005 | REQ-PROD-003, REQ-PROD-005 | Verify cart-indicator behavior when multiple products are added from the product listing. | Positive / Functional | High |
| TS-PROD-006 | REQ-PROD-004, REQ-PROD-005 | Verify cart-indicator behavior when one product is removed while other products remain selected. | Positive / Functional | High |
| TS-PROD-007 | REQ-PROD-006 | Verify that products can be sorted alphabetically from A to Z. | Functional / Sorting | Medium |
| TS-PROD-008 | REQ-PROD-007 | Verify that products can be sorted alphabetically from Z to A. | Functional / Sorting | Medium |
| TS-PROD-009 | REQ-PROD-008 | Verify that products can be sorted by price from lowest to highest. | Functional / Sorting | Medium |
| TS-PROD-010 | REQ-PROD-009 | Verify that products can be sorted by price from highest to lowest. | Functional / Sorting | Medium |

---

## Scenario Design Rationale

The Product Listing scenarios provide coverage of three primary behavior groups.

### Product Presentation

The application should display available products and provide enough information for a user to identify each item.

Covered by:

`TS-PROD-001`  
`TS-PROD-002`

### Product Selection and Cart Indicator

Users should be able to add and remove products directly from the inventory page.

The shopping-cart indicator should remain consistent with the number of currently selected products.

Covered by:

`TS-PROD-003`  
`TS-PROD-004`  
`TS-PROD-005`  
`TS-PROD-006`

### Product Sorting

The product list should support the available name and price sorting options.

Covered by:

`TS-PROD-007`  
`TS-PROD-008`  
`TS-PROD-009`  
`TS-PROD-010`

---

## Test Design Techniques

### Equivalence Partitioning

Sorting behavior is divided into representative sorting modes:

- Name ascending
- Name descending
- Price ascending
- Price descending

Each available sorting mode represents a distinct behavioral partition.

### State Transition Testing

Product-selection behavior changes the cart state.

Example:

`Cart = 0`

→ Add Product A

→ `Cart = 1`

→ Add Product B

→ `Cart = 2`

→ Remove Product A

→ `Cart = 1`

These transitions will be verified through the cart indicator.

### Workflow-Based Testing

Product-listing tests also verify the interaction between product selection and the shopping-cart state without yet testing the complete Shopping Cart module.

---

## Requirement Coverage

The Product Listing & Sorting scenarios provide planned coverage for:

- `REQ-PROD-001`
- `REQ-PROD-002`
- `REQ-PROD-003`
- `REQ-PROD-004`
- `REQ-PROD-005`
- `REQ-PROD-006`
- `REQ-PROD-007`
- `REQ-PROD-008`
- `REQ-PROD-009`

Detailed test cases will provide test data, execution steps, and expected results.
# MOD-03 — Product Details

## Scenario Coverage

| Scenario ID | Related Requirement(s) | Test Scenario | Test Type | Priority |
|---|---|---|---|---|
| TS-PDETAIL-001 | REQ-PDETAIL-001 | Verify that a user can open an individual product from the product listing. | Positive / Functional | Medium |
| TS-PDETAIL-002 | REQ-PDETAIL-002 | Verify that the product details page displays information corresponding to the selected product. | Positive / Functional | Medium |
| TS-PDETAIL-003 | REQ-PDETAIL-003 | Verify that a product can be added to the shopping cart from the product details page. | Positive / Functional | High |
| TS-PDETAIL-004 | REQ-PDETAIL-004 | Verify that an added product can be removed from the product details page. | Positive / Functional | High |
| TS-PDETAIL-005 | REQ-PDETAIL-005 | Verify that the user can return from the product details page to the product listing. | Positive / Navigation | Medium |
| TS-PDETAIL-006 | REQ-PDETAIL-002 | Verify that different selected products display their corresponding product information. | Data Consistency / Functional | Medium |

---

## Scenario Design Rationale

The Product Details scenarios validate navigation into an individual product, consistency between the selected product and displayed information, cart actions from the details page, and return navigation.

## Requirement Coverage

The Product Details scenarios provide planned coverage for:

- REQ-PDETAIL-001
- REQ-PDETAIL-002
- REQ-PDETAIL-003
- REQ-PDETAIL-004
- REQ-PDETAIL-005
# MOD-04 — Shopping Cart

## Scenario Coverage

| Scenario ID | Related Requirement(s) | Test Scenario | Test Type | Priority |
|---|---|---|---|---|
| TS-CART-001 | REQ-CART-001 | Verify that a product added from the product listing is displayed in the shopping cart. | Positive / Functional | High |
| TS-CART-002 | REQ-CART-001, REQ-CART-002 | Verify that multiple selected products are displayed correctly in the shopping cart. | Positive / Functional | High |
| TS-CART-003 | REQ-CART-002 | Verify that product information displayed in the cart corresponds to the selected product. | Data Consistency / Functional | High |
| TS-CART-004 | REQ-CART-003 | Verify that a product can be removed directly from the shopping cart. | Positive / Functional | High |
| TS-CART-005 | REQ-CART-003, REQ-CART-006 | Verify that one product can be removed while other selected products remain in the cart. | State Transition / Functional | High |
| TS-CART-006 | REQ-CART-004 | Verify that the user can return from the shopping cart to product browsing. | Navigation / Functional | Medium |
| TS-CART-007 | REQ-CART-005 | Verify that the user can proceed from the shopping cart to the checkout workflow. | Positive / Functional | High |
| TS-CART-008 | REQ-CART-006 | Verify that shopping-cart contents remain consistent when navigating between the Products page and the Cart page. | State Persistence / Functional | High |
| TS-CART-009 | REQ-CART-001, REQ-CART-006 | Verify the behavior of the shopping cart when no products have been selected. | Edge Case / Functional | Medium |

---

## Scenario Design Rationale

The Shopping Cart scenarios validate product visibility, data consistency, item removal, navigation, checkout entry, and cart-state consistency.

### Cart Content Validation

The shopping cart should accurately represent products selected by the user.

Covered by:

`TS-CART-001`  
`TS-CART-002`  
`TS-CART-003`

### Cart Modification

Users should be able to remove selected products while maintaining the correct state of any remaining items.

Covered by:

`TS-CART-004`  
`TS-CART-005`

### Navigation and Checkout

The cart acts as an intermediate stage between product browsing and checkout.

Covered by:

`TS-CART-006`  
`TS-CART-007`

### Cart State Persistence

Cart contents should remain consistent during normal application navigation unless the user explicitly removes an item or resets the application state.

Covered by:

`TS-CART-008`

### Empty Cart Behavior

The shopping cart should also be evaluated when no products have been selected.

Covered by:

`TS-CART-009`

---

## Test Design Techniques

### State Transition Testing

Shopping-cart behavior involves transitions between different cart states.

Example:

`Cart = 0`

→ Add Product A

→ `Cart = 1`

→ Add Product B

→ `Cart = 2`

→ Remove Product A

→ `Cart = 1`

→ Remove Product B

→ `Cart = 0`

### Workflow-Based Testing

Shopping-cart testing validates interaction across multiple functional areas:

Products

→ Shopping Cart

→ Continue Shopping

→ Shopping Cart

→ Checkout

### Positive Testing

Valid user workflows such as adding products, reviewing the cart, and proceeding to checkout will be verified.

### Edge-Case Testing

The shopping cart will also be evaluated when it contains no selected products.

---

## Requirement Coverage

The Shopping Cart scenarios provide planned coverage for:

- `REQ-CART-001`
- `REQ-CART-002`
- `REQ-CART-003`
- `REQ-CART-004`
- `REQ-CART-005`
- `REQ-CART-006`

Detailed test cases will provide test data, execution steps, and expected results.
# MOD-05 — Checkout Customer Information

## Scenario Coverage

| Scenario ID | Related Requirement(s) | Test Scenario | Test Type | Priority |
|---|---|---|---|---|
| TS-CHKINFO-001 | REQ-CHKINFO-001, REQ-CHKINFO-002, REQ-CHKINFO-003, REQ-CHKINFO-006 | Verify successful checkout progression when valid customer information is provided. | Positive / Functional | High |
| TS-CHKINFO-002 | REQ-CHKINFO-004, REQ-CHKINFO-005 | Verify validation when First Name is missing. | Negative / Validation | High |
| TS-CHKINFO-003 | REQ-CHKINFO-004, REQ-CHKINFO-005 | Verify validation when Last Name is missing. | Negative / Validation | High |
| TS-CHKINFO-004 | REQ-CHKINFO-004, REQ-CHKINFO-005 | Verify validation when Postal Code is missing. | Negative / Validation | High |
| TS-CHKINFO-005 | REQ-CHKINFO-004, REQ-CHKINFO-005 | Verify validation when all customer information fields are empty. | Negative / Validation | High |
| TS-CHKINFO-006 | REQ-CHKINFO-001, REQ-CHKINFO-002, REQ-CHKINFO-003 | Verify that valid customer information can be entered into all required fields. | Positive / Functional | Medium |
| TS-CHKINFO-007 | REQ-CHKINFO-007 | Verify that Cancel returns the user from checkout information to the shopping cart. | Navigation / Functional | High |
| TS-CHKINFO-008 | REQ-CHKINFO-004, REQ-CHKINFO-005 | Verify validation when only First Name is entered. | Negative / Validation | Medium |
| TS-CHKINFO-009 | REQ-CHKINFO-004, REQ-CHKINFO-005 | Verify validation when First Name and Last Name are entered but Postal Code is missing. | Negative / Validation | Medium |

---

## Scenario Design Rationale

The Checkout Customer Information scenarios validate required-field behavior, successful data entry, negative validation, error handling, and navigation back to the cart.

### Successful Customer Information Entry

Covered by:

`TS-CHKINFO-001`  
`TS-CHKINFO-006`

### Required Field Validation

Covered by:

`TS-CHKINFO-002`  
`TS-CHKINFO-003`  
`TS-CHKINFO-004`  
`TS-CHKINFO-005`  
`TS-CHKINFO-008`  
`TS-CHKINFO-009`

### Navigation

Covered by:

`TS-CHKINFO-007`

---

## Test Design Techniques

### Equivalence Partitioning

Input states are divided into valid and invalid classes.

Examples:

- All required fields valid
- Missing First Name
- Missing Last Name
- Missing Postal Code
- All required fields empty

### Negative Testing

Incomplete customer information is intentionally submitted to confirm that the application prevents invalid progression.

### Workflow Testing

The module is tested as part of the checkout workflow:

Products

→ Shopping Cart

→ Checkout Customer Information

→ Checkout Overview

and:

Shopping Cart

→ Checkout Customer Information

→ Cancel

→ Shopping Cart

---

## Requirement Coverage

The Checkout Customer Information scenarios provide planned coverage for:

- `REQ-CHKINFO-001`
- `REQ-CHKINFO-002`
- `REQ-CHKINFO-003`
- `REQ-CHKINFO-004`
- `REQ-CHKINFO-005`
- `REQ-CHKINFO-006`
- `REQ-CHKINFO-007`

Detailed test cases will provide test data, execution steps, and expected results.
# MOD-06 — Checkout Order Overview

## Scenario Coverage

| Scenario ID | Related Requirement(s) | Test Scenario | Test Type | Priority |
|---|---|---|---|---|
| TS-CHKOV-001 | REQ-CHKOV-001 | Verify that selected products are displayed on the checkout overview page. | Positive / Functional | High |
| TS-CHKOV-002 | REQ-CHKOV-002 | Verify that product pricing on the checkout overview corresponds to the selected products. | Data Consistency / Functional | High |
| TS-CHKOV-003 | REQ-CHKOV-003 | Verify that the item subtotal corresponds to the sum of selected product prices. | Calculation / Functional | High |
| TS-CHKOV-004 | REQ-CHKOV-004 | Verify that tax is displayed separately on the checkout overview. | Calculation / Functional | High |
| TS-CHKOV-005 | REQ-CHKOV-003, REQ-CHKOV-004, REQ-CHKOV-005 | Verify that the final total corresponds to item subtotal plus tax. | Calculation / Functional | High |
| TS-CHKOV-006 | REQ-CHKOV-006 | Verify that the user can finish the order from the checkout overview. | Positive / Workflow | High |
| TS-CHKOV-007 | REQ-CHKOV-007 | Verify that the user can cancel from the checkout overview without completing the order. | Navigation / Functional | High |

---

## Scenario Design Rationale

The Checkout Order Overview scenarios validate order contents, product pricing, financial calculations, and user actions available before final order submission.

### Order Content Validation

Covered by:

`TS-CHKOV-001`  
`TS-CHKOV-002`

### Calculation Validation

Covered by:

`TS-CHKOV-003`  
`TS-CHKOV-004`  
`TS-CHKOV-005`

### Checkout Workflow

Covered by:

`TS-CHKOV-006`  
`TS-CHKOV-007`

---

## Test Design Techniques

### Data Consistency Testing

Products and prices shown during checkout should correspond to the products selected earlier in the shopping workflow.

### Calculation Testing

The following relationship will be validated:

Item Subtotal

+

Tax

=

Final Total

### Workflow Testing

The checkout overview is tested within the complete purchasing workflow:

Products

→ Shopping Cart

→ Checkout Customer Information

→ Checkout Order Overview

→ Order Completion

---

## Requirement Coverage

The Checkout Order Overview scenarios provide planned coverage for:

- `REQ-CHKOV-001`
- `REQ-CHKOV-002`
- `REQ-CHKOV-003`
- `REQ-CHKOV-004`
- `REQ-CHKOV-005`
- `REQ-CHKOV-006`
- `REQ-CHKOV-007`

Detailed test cases will provide test data, execution steps, and expected results.
# MOD-07 — Order Completion

## Scenario Coverage

| Scenario ID | Related Requirement(s) | Test Scenario | Test Type | Priority |
|---|---|---|---|---|
| TS-ORDER-001 | REQ-ORDER-001 | Verify that an order-completion page is displayed after finishing a valid checkout. | Positive / Functional | High |
| TS-ORDER-002 | REQ-ORDER-002 | Verify that successful order completion is clearly communicated to the user. | Positive / Functional | High |
| TS-ORDER-003 | REQ-ORDER-003 | Verify that the user can return to the Products inventory after completing an order. | Navigation / Functional | Medium |

---

## Scenario Design Rationale

The Order Completion scenarios validate the final stage of the end-to-end purchasing workflow.

### Successful Order Completion

Covered by:

`TS-ORDER-001`  
`TS-ORDER-002`

### Post-Order Navigation

Covered by:

`TS-ORDER-003`

---

## Test Design Techniques

### Workflow Testing

The complete order workflow is validated across:

Login

→ Products

→ Shopping Cart

→ Checkout Customer Information

→ Checkout Order Overview

→ Finish

→ Order Completion

### Navigation Testing

Post-order navigation is validated to ensure that the user can return to the Products inventory after completing an order.

---

## Requirement Coverage

The Order Completion scenarios provide planned coverage for:

- `REQ-ORDER-001`
- `REQ-ORDER-002`
- `REQ-ORDER-003`

Detailed test cases will provide test data, execution steps, and expected results.
# MOD-08 — Navigation, Menu and Session

## Scenario Coverage

| Scenario ID | Related Requirement(s) | Test Scenario | Test Type | Priority |
|---|---|---|---|---|
| TS-NAV-001 | REQ-NAV-001 | Verify that an authenticated user can open the application navigation menu. | Positive / Functional | Medium |
| TS-NAV-002 | REQ-NAV-002 | Verify that All Items navigates the user to the Products inventory. | Navigation / Functional | Medium |
| TS-NAV-003 | REQ-NAV-003 | Verify that About navigates to the configured external destination. | Navigation / Functional | Medium |
| TS-NAV-004 | REQ-NAV-004 | Verify that Reset App State clears the user's current application state. | State Transition / Functional | High |
| TS-NAV-005 | REQ-NAV-005 | Verify that an authenticated user can log out successfully. | Positive / Session | High |
| TS-NAV-006 | REQ-NAV-006 | Verify that protected application functionality cannot be normally accessed after logout without authenticating again. | Negative / Session | High |

---

## Scenario Design Rationale

The Navigation, Menu and Session scenarios validate application navigation, application-state management, logout behavior, and session termination.

### Application Navigation

Covered by:

`TS-NAV-001`  
`TS-NAV-002`  
`TS-NAV-003`

### Application State Management

Covered by:

`TS-NAV-004`

### Session Management

Covered by:

`TS-NAV-005`  
`TS-NAV-006`

---

## Test Design Techniques

### Navigation Testing

Navigation controls are verified to ensure that each menu action takes the user to the expected destination.

### State Transition Testing

Reset App State validates the transition from a populated application state to a clean state.

Example:

Cart = 2

→ Reset App State

→ Cart = 0

### Negative Testing

After logout, protected authenticated functionality is accessed again intentionally to verify that the terminated session is not restored.

---

## Requirement Coverage

The Navigation, Menu and Session scenarios provide planned coverage for:

- `REQ-NAV-001`
- `REQ-NAV-002`
- `REQ-NAV-003`
- `REQ-NAV-004`
- `REQ-NAV-005`
- `REQ-NAV-006`

Detailed test cases will provide test data, execution steps, and expected results.
