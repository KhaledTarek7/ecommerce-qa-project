# Functional Requirements

## 1. Purpose

This document defines the functional requirements used as the basis for testing the SauceDemo e-commerce web application.

Because no formal Business Requirements Document (BRD), Product Requirements Document (PRD), or Software Requirements Specification (SRS) is provided for this QA portfolio project, the requirements in this document are classified as **derived requirements**.

They are based on observable application functionality, expected user workflows, and documented QA assumptions.

---

## 2. Requirement Classification

**Source:** Derived

The requirements documented in this project are not presented as official Sauce Labs business requirements.

They represent the expected behavior against which the application will be tested.

---

# MOD-01 — Authentication / Login

| Requirement ID | Requirement                                                                              | Priority |
| -------------- | ---------------------------------------------------------------------------------------- | -------- |
| REQ-LOGIN-001  | The system shall provide username and password fields for user authentication.           | High     |
| REQ-LOGIN-002  | The system shall allow an authorized user to log in using valid credentials.             | High     |
| REQ-LOGIN-003  | The system shall prevent authentication when invalid credentials are provided.           | High     |
| REQ-LOGIN-004  | The system shall prevent login when the username is missing.                             | High     |
| REQ-LOGIN-005  | The system shall prevent login when the password is missing.                             | High     |
| REQ-LOGIN-006  | The system shall display an appropriate error message when authentication fails.         | High     |
| REQ-LOGIN-007  | The system shall prevent a locked-out user from accessing the authenticated application. | High     |

---

# MOD-02 — Product Listing & Sorting

| Requirement ID | Requirement                                                                                       | Priority |
| -------------- | ------------------------------------------------------------------------------------------------- | -------- |
| REQ-PROD-001   | The system shall display the available products after successful authentication.                  | High     |
| REQ-PROD-002   | Each listed product shall display sufficient product information to identify the item.            | Medium   |
| REQ-PROD-003   | The user shall be able to add an available product to the shopping cart from the product listing. | High     |
| REQ-PROD-004   | The user shall be able to remove a previously added product from the product listing.             | High     |
| REQ-PROD-005   | The shopping cart indicator shall reflect the number of products currently added to the cart.     | High     |
| REQ-PROD-006   | The user shall be able to sort products alphabetically in ascending order.                        | Medium   |
| REQ-PROD-007   | The user shall be able to sort products alphabetically in descending order.                       | Medium   |
| REQ-PROD-008   | The user shall be able to sort products by price from lowest to highest.                          | Medium   |
| REQ-PROD-009   | The user shall be able to sort products by price from highest to lowest.                          | Medium   |

---

# MOD-03 — Product Details

| Requirement ID  | Requirement                                                                                             | Priority |
| --------------- | ------------------------------------------------------------------------------------------------------- | -------- |
| REQ-PDETAIL-001 | The user shall be able to open the details of an individual product from the product listing.           | Medium   |
| REQ-PDETAIL-002 | The product details page shall display information corresponding to the selected product.               | Medium   |
| REQ-PDETAIL-003 | The user shall be able to add the displayed product to the shopping cart from the product details page. | High     |
| REQ-PDETAIL-004 | The user shall be able to remove an added product from the product details page.                        | High     |
| REQ-PDETAIL-005 | The user shall be able to return from the product details page to the product listing.                  | Medium   |

---

# MOD-04 — Shopping Cart

| Requirement ID | Requirement                                                                                                                                                   | Priority |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| REQ-CART-001   | The shopping cart shall display products that have been added by the user.                                                                                    | High     |
| REQ-CART-002   | The shopping cart shall display information corresponding to each selected product.                                                                           | High     |
| REQ-CART-003   | The user shall be able to remove products from the shopping cart.                                                                                             | High     |
| REQ-CART-004   | The user shall be able to return to product browsing from the shopping cart.                                                                                  | Medium   |
| REQ-CART-005   | The user shall be able to proceed from the shopping cart to the checkout workflow.                                                                            | High     |
| REQ-CART-006   | Cart contents shall remain consistent while the user navigates through the shopping workflow unless the user removes an item or resets the application state. | High     |

---

# MOD-05 — Checkout: Customer Information

| Requirement ID  | Requirement                                                                                               | Priority |
| --------------- | --------------------------------------------------------------------------------------------------------- | -------- |
| REQ-CHKINFO-001 | The checkout process shall request the customer's first name.                                             | High     |
| REQ-CHKINFO-002 | The checkout process shall request the customer's last name.                                              | High     |
| REQ-CHKINFO-003 | The checkout process shall request the customer's postal code.                                            | High     |
| REQ-CHKINFO-004 | The system shall prevent the user from continuing when required checkout information is missing.          | High     |
| REQ-CHKINFO-005 | The system shall display an appropriate validation message when required checkout information is missing. | High     |
| REQ-CHKINFO-006 | The user shall be able to continue to the order overview after providing valid required information.      | High     |
| REQ-CHKINFO-007 | The user shall be able to cancel the checkout information stage and return to the shopping cart.          | Medium   |

---

# MOD-06 — Checkout: Order Overview

| Requirement ID | Requirement                                                             | Priority |
| -------------- | ----------------------------------------------------------------------- | -------- |
| REQ-CHKOV-001  | The checkout overview shall display the products included in the order. | High     |
| REQ-CHKOV-002  | The checkout overview shall display pricing information for the order.  | High     |
| REQ-CHKOV-003  | The checkout overview shall display an item subtotal.                   | High     |
| REQ-CHKOV-004  | The checkout overview shall display applicable tax information.         | High     |
| REQ-CHKOV-005  | The checkout overview shall display the final order total.              | High     |
| REQ-CHKOV-006  | The user shall be able to finish the order from the checkout overview.  | High     |
| REQ-CHKOV-007  | The user shall be able to cancel the order from the checkout overview.  | Medium   |

---

# MOD-07 — Order Completion

| Requirement ID | Requirement                                                                         | Priority |
| -------------- | ----------------------------------------------------------------------------------- | -------- |
| REQ-ORDER-001  | The system shall display confirmation after an order is successfully completed.     | High     |
| REQ-ORDER-002  | A completed checkout shall represent the successful end of the purchasing workflow. | High     |
| REQ-ORDER-003  | The user shall be able to return to the product area after completing an order.     | Medium   |

---

# MOD-08 — Navigation, Menu & Session

| Requirement ID | Requirement                                                                            | Priority |
| -------------- | -------------------------------------------------------------------------------------- | -------- |
| REQ-NAV-001    | An authenticated user shall be able to access the application navigation menu.         | Medium   |
| REQ-NAV-002    | The user shall be able to navigate to the product listing using the menu.              | Medium   |
| REQ-NAV-003    | The menu shall provide access to the application's About destination.                  | Low      |
| REQ-NAV-004    | The user shall be able to reset the application state using the available menu option. | Medium   |
| REQ-NAV-005    | The authenticated user shall be able to log out of the application.                    | High     |
| REQ-NAV-006    | After logout, the user shall no longer remain in an authenticated application session. | High     |

---

# 3. Requirement Prioritization

Requirements are initially classified using three priority levels.

**High**

Failure may block or significantly affect a critical business workflow such as authentication, cart management, checkout, or order completion.

**Medium**

Failure affects functionality or usability but may not completely prevent completion of the primary purchase workflow.

**Low**

Failure has limited impact on the primary business journey.

Requirement priorities may be refined during test planning and risk analysis.

---

# 4. Assumptions

| Assumption ID | Assumption                                                                                                       |
| ------------- | ---------------------------------------------------------------------------------------------------------------- |
| ASM-001       | SauceDemo is treated as a test/demo e-commerce application rather than a production commerce platform.           |
| ASM-002       | Predefined application users are treated as controlled test personas.                                            |
| ASM-003       | No customer registration workflow is expected because registration is not available in the observed application. |
| ASM-004       | No product-search workflow is expected because product search is not available in the observed application.      |
| ASM-005       | Checkout represents a simulated purchasing process and does not require real payment processing.                 |
| ASM-006       | Requirements may be refined if application exploration reveals additional expected behavior.                     |

---

# 5. Traceability

Each requirement will later be mapped to one or more test scenarios and test cases.

Example:

`REQ-LOGIN-002`

→ `TS-LOGIN-001`

→ `TC-LOGIN-001`

→ Test Execution

→ PASS / FAIL

→ Defect if applicable

This relationship will later be maintained through the Requirements Traceability Matrix and Jira/Zephyr.
