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
