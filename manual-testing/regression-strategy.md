# SauceDemo Regression Testing Strategy

## 1. Purpose

Regression testing is intended to verify that previously validated SauceDemo functionality continues to operate correctly after application changes.

The existing functional test repository acts as the source for regression test selection.

---

## 2. Regression Testing Objective

The objective of regression testing is to identify unintended effects introduced by changes to the application.

Regression testing should confirm that previously working functionality remains operational after modifications, fixes, deployments, or configuration changes.

---

## 3. Regression Triggers

Regression execution should be considered after:

- New feature implementation
- Existing feature modification
- Defect fixes
- Significant user-interface changes
- Application configuration changes
- Dependency or environment changes
- Release candidate deployment
- Changes affecting shared application components

---

## 4. Regression Scope

Regression test cases will be selected from the existing functional test suite based on:

- Business criticality
- Change impact
- Requirement dependencies
- Previous defect history
- Integration with modified functionality
- Risk of unintended side effects
- Automation suitability

The existing test repository contains functional coverage across:

- Authentication and Login
- Product Listing and Sorting
- Product Details
- Shopping Cart
- Checkout Customer Information
- Checkout Order Overview
- Order Completion
- Navigation and Session Management

---

## 5. Regression Test Selection

Regression testing will reuse existing Zephyr test cases rather than creating duplicate test cases.

The extent of regression execution will depend on the impact of the application change.

### Targeted Regression

Used when a change affects a limited functional area.

Example:

A modification to checkout validation may require regression coverage across:

- Checkout Customer Information
- Shopping Cart
- Checkout Order Overview

### Broad Regression

Used when a change affects shared application functionality or a major release is deployed.

A broader selection of functional test cases may then be executed across multiple modules.

---

## 6. Relationship with Smoke Testing

Smoke testing provides rapid confirmation that the critical application workflow is operational.

Regression testing provides broader confidence that existing functionality has not been negatively affected by a change.

Typical execution sequence:

Smoke Testing

→ Smoke Pass

→ Regression Testing

→ Detailed Validation

---

## 7. Current Project Status

A complete functional baseline has been established for the identified SauceDemo modules.

A dedicated smoke test suite has also been executed.

No regression execution was performed during the initial baseline because no application modification, defect fix, or new deployment occurred between the functional testing and smoke testing phases.

Executing regression testing without a relevant application change would not provide meaningful additional validation.

Regression testing will therefore be triggered when a future change provides a valid regression-testing reason.

---

## 8. Future Automation

High-value regression scenarios will be automated using:

- Python
- Selenium WebDriver
- pytest
- Page Object Model
- Explicit waits
- Reusable fixtures
- GitHub Actions

Automated regression tests will eventually be executed through CI after relevant application or automation changes.

---

## 9. Status

Current Regression Execution Status:

**Not Executed — No Regression Trigger**

This status reflects a deliberate risk-based testing decision rather than missing test coverage.
