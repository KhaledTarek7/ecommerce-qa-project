# SauceDemo Smoke Test Suite

## 1. Purpose

The Smoke Test Suite provides rapid validation of the most critical SauceDemo business workflow after a new build, deployment, or significant environment change.

The suite is intentionally small and focuses on confirming that the application is stable enough for further functional or regression testing.

---

## 2. Smoke Testing Objective

The smoke suite validates the critical end-to-end customer journey:

Login

→ Product Selection

→ Shopping Cart

→ Checkout Information

→ Checkout Overview

→ Order Completion

→ Logout

If a critical smoke test fails, broader regression execution may be suspended until the failure is investigated.

---

## 3. Selected Smoke Test Cases

| Test Case | Area | Reason for Inclusion |
|---|---|---|
| TC-LOGIN-001 | Authentication | Confirms that a valid user can access the application. |
| TC-PROD-003 | Product Listing | Confirms that a product can be selected for purchase. |
| TC-CART-001 | Shopping Cart | Confirms that the selected product reaches the cart. |
| TC-CART-007 | Shopping Cart / Checkout | Confirms that checkout can be initiated. |
| TC-CHKINFO-001 | Checkout Information | Confirms that valid customer information allows checkout progression. |
| TC-CHKOV-005 | Checkout Overview | Confirms that the final order total is calculated consistently. |
| TC-CHKOV-006 | Checkout Overview | Confirms that the order can be submitted. |
| TC-ORDER-002 | Order Completion | Confirms successful order completion. |
| TC-NAV-005 | Session Management | Confirms that the user can terminate the authenticated session. |

---

## 4. Entry Criteria

Smoke testing may begin when:

- SauceDemo is accessible.
- The test environment is available.
- The standard test user can be used.
- A new build, deployment, or test execution baseline is available.

---

## 5. Exit Criteria

Smoke testing passes when:

- All critical smoke test cases have been executed.
- No critical smoke test has failed.
- No blocking defect prevents continuation of testing.

If a critical smoke test fails, further regression testing may be suspended pending investigation.

---

## 6. Test Environment

Application: SauceDemo

Primary Browser: Google Chrome — Desktop Web

Primary User:

`standard_user`

---

## 7. Execution Management

The smoke test cases are maintained as reusable Zephyr test cases.

They are executed through a dedicated:

`SauceDemo Smoke Test Cycle`

Existing test cases are reused rather than duplicated.
