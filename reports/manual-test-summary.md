# Manual Functional Test Summary

## 1. Overview

This report summarizes the manual functional testing performed against the SauceDemo e-commerce application.

Testing was executed using a risk-based black-box approach covering the complete user workflow from authentication through order completion and session termination.

Test cases were managed and executed using Jira and Zephyr Essential.

---

## 2. Scope

The following functional modules were tested:

| Module | Test Cases |
|---|---:|
| MOD-01 — Authentication / Login | 8 |
| MOD-02 — Product Listing & Sorting | 10 |
| MOD-03 — Product Details | 6 |
| MOD-04 — Shopping Cart | 9 |
| MOD-05 — Checkout Customer Information | 9 |
| MOD-06 — Checkout Order Overview | 7 |
| MOD-07 — Order Completion | 3 |
| MOD-08 — Navigation, Menu & Session | 6 |
| **Total** | **58** |

---

## 3. Test Types Covered

The manual test suite includes:

- Positive functional testing
- Negative testing
- Validation testing
- Navigation testing
- State-transition testing
- Data-consistency testing
- Calculation testing
- Workflow testing
- Session testing
- Edge-case testing

---

## 4. Test Environment

Application:

SauceDemo

URL:

https://www.saucedemo.com/

Primary Browser:

Google Chrome — Desktop Web

Primary Test User:

standard_user

---

## 5. Execution Summary

| Metric | Result |
|---|---:|
| Total Test Cases | 58 |
| Executed | 58 |
| Passed | Update from final Zephyr report |
| Failed | Update from final Zephyr report |
| Blocked | Update from final Zephyr report |
| Execution Completion | Update from final Zephyr report |
| Pass Rate | Update from final Zephyr report |

---

## 6. Functional Coverage

The executed test suite covered the complete primary purchasing workflow:

Login

→ Product Browsing

→ Product Details

→ Shopping Cart

→ Checkout Customer Information

→ Checkout Order Overview

→ Order Completion

→ Logout / Session Termination

---

## 7. Traceability

Functional requirements were mapped to:

- Jira Stories
- Test Scenarios
- Zephyr Test Cases
- Test Cycles
- Execution Results

This provides traceability from requirement definition through test execution.

A dedicated Requirements Traceability Matrix will provide consolidated requirement-level coverage.

---

## 8. Conclusion

The functional manual-testing phase established baseline behavioral coverage for all identified SauceDemo functional modules.

The resulting test suite will be reused to define smoke and regression coverage and to identify high-value candidates for test automation.

Manual testing will be followed by exploratory testing, regression-suite definition, Selenium-based automation, CI integration, and AI-assisted quality analysis.
