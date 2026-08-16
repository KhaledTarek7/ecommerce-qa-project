# Test Strategy

## 1. Purpose

This document defines the overall testing strategy for the **E-Commerce QA & Test Automation Project** based on the SauceDemo / Swag Labs web application.

The strategy describes how testing will be approached across manual testing, test management, automation, defect management, regression testing, BDD, and CI/CD.

The objective is to provide adequate functional coverage of the application's critical user journeys while maintaining traceability between requirements, test cases, execution results, defects, and automated tests.

---

## 2. Testing Objectives

The testing activities will aim to:

* Validate the main functional workflows of the application.
* Verify that critical user journeys behave as expected.
* Identify functional and usability defects.
* Validate positive, negative, and boundary conditions.
* Prioritize testing based on business and functional risk.
* Maintain traceability between requirements and test coverage.
* Establish repeatable regression coverage.
* Automate stable and business-critical scenarios.
* Integrate automated tests into a CI workflow.
* Produce clear testing evidence and reports.

---

## 3. Testing Approach

The project will primarily use a **black-box testing approach**.

Testing will focus on the externally observable behavior of the application rather than its internal implementation.

The project will use a combination of:

* Requirement-based testing
* Risk-based testing
* Exploratory testing
* Positive testing
* Negative testing
* Boundary and edge-case testing
* Regression testing
* Automated UI testing

---

## 4. Risk-Based Testing

Testing effort will be prioritized based on the impact of failure on the primary e-commerce workflow.

### High-Risk Areas

* Authentication
* Shopping cart
* Checkout
* Order completion
* Session termination

Failures in these areas may prevent the user from accessing or completing the primary purchasing workflow.

### Medium-Risk Areas

* Product listing
* Product sorting
* Product details
* General navigation

Failures may affect functionality or usability but may not always block the full purchasing process.

### Low-Risk Areas

* Cosmetic or non-critical navigation behaviors
* Minor visual inconsistencies
* Non-critical informational links

High-risk functionality will receive deeper manual coverage and will be prioritized for automation.

---

## 5. Test Levels and Test Scope

Because this project treats SauceDemo as an externally accessible web application, the primary testing level will be **system testing**.

The project will also perform end-to-end workflow validation across multiple functional modules.

The project will not perform unit testing because access to and ownership of the application's internal source-code unit tests are outside the scope of this QA portfolio.

---

## 6. Test Types

### 6.1 Functional Testing

Functional testing will verify that application features behave according to the documented derived requirements.

Examples include:

* Login
* Product browsing
* Cart operations
* Checkout
* Order completion
* Logout

### 6.2 Positive Testing

Positive tests will validate expected behavior using valid inputs and valid user workflows.

Example:

A valid user logs in using correct credentials.

### 6.3 Negative Testing

Negative testing will validate how the application behaves when invalid or incomplete inputs are provided.

Examples include:

* Invalid login credentials
* Missing username
* Missing password
* Missing checkout information

### 6.4 Boundary and Edge-Case Testing

Boundary and edge testing will be applied where relevant.

Examples may include:

* Empty fields
* Unusual input lengths
* Special characters
* Navigation between workflow stages
* Empty shopping cart behavior

### 6.5 UI Testing

UI testing will verify that important interface elements are present, accessible, and functionally usable.

The project will not attempt full visual-regression certification.

### 6.6 Integration / Workflow Testing

Integration-oriented functional testing will verify interactions between application modules.

Example:

Product Listing
→ Add Product
→ Cart
→ Checkout
→ Order Completion

### 6.7 Smoke Testing

A small set of critical tests will be used to determine whether the application is stable enough for further testing.

The smoke suite will focus on critical functionality such as:

* Successful login
* Product page availability
* Add to cart
* Access checkout
* Logout

### 6.8 Sanity Testing

Sanity testing will be used after a focused change or defect fix to confirm that the affected functionality behaves correctly before broader regression testing.

### 6.9 Regression Testing

Regression testing will validate that previously working functionality remains operational after changes or fixes.

Regression coverage will include both manual and automated tests.

High-risk and frequently repeated test cases will receive priority for automation.

### 6.10 Exploratory Testing

Exploratory testing will be used to identify unexpected behavior that may not be covered by predefined test cases.

Different SauceDemo test personas may be used during exploratory testing to investigate unusual or failure-oriented behaviors.

---

## 7. Manual Testing Strategy

Manual testing will be performed before automation.

The manual testing workflow will follow:

Requirements
→ Test Scenarios
→ Test Cases
→ Test Data
→ Test Execution
→ Defect Reporting
→ Retesting
→ Regression

Manual testing will establish the expected behavior of the application before automated tests are created.

---

## 8. Test Case Design Techniques

The following test design techniques will be used where applicable:

* Equivalence Partitioning
* Boundary Value Analysis
* Decision-based test design
* Positive and negative testing
* Error guessing
* Exploratory testing
* Use-case / workflow-based testing

Not every technique will be applied to every requirement.

The technique will be selected based on the nature of the functionality being tested.

---

## 9. Test Data Strategy

Test data will be controlled and documented.

The primary test account for baseline functional testing will be:

`standard_user`

Additional predefined personas will be used for targeted testing, including:

* `locked_out_user`
* `problem_user`
* `performance_glitch_user`
* `error_user`
* `visual_user`

Sensitive production data will not be used.

Test data used in automation will later be separated from page logic where practical.

---

## 10. Defect Management Strategy

Defects discovered during execution will be documented in Jira.

Each defect should include:

* Clear title
* Environment
* Preconditions
* Steps to reproduce
* Actual result
* Expected result
* Severity
* Priority
* Evidence where applicable
* Related requirement
* Related test case

Failed Zephyr test executions will be linked to the corresponding Jira defect where applicable.

The defect lifecycle will follow approximately:

New
→ Open / In Progress
→ Fixed
→ Retest
→ Closed

If the issue is still reproducible during retesting, it will be reopened.

---

## 11. Test Management Strategy

Jira will be used for:

* Requirements / stories
* Tasks
* Defects
* Work tracking

Zephyr will be used for:

* Test case management
* Test organization
* Test cycles
* Test execution
* Execution results
* Requirement-to-test traceability

The intended relationship is:

Requirement / Jira Story
→ Zephyr Test Case
→ Test Cycle
→ Test Execution
→ PASS / FAIL
→ Jira Defect if required
→ Retest

---

## 12. Automation Strategy

Automation will begin only after the core application behavior has been understood and manually validated.

The automation framework will use:

* Python
* Selenium WebDriver
* pytest
* Page Object Model
* pytest fixtures
* Explicit waits
* Assertions
* Reusable utilities
* Externalized test data where appropriate
* HTML reporting

Automation will focus primarily on:

* Critical business workflows
* Stable functionality
* Regression scenarios
* Repetitive test cases
* High-risk functionality

Not every manual test case will be automated.

---

## 13. BDD Strategy

BDD concepts will be demonstrated using **Behave** with Gherkin syntax.

Feature files will describe selected user behaviors using:

* Given
* When
* Then
* And

BDD scenarios will reuse the automation framework where practical instead of duplicating browser logic.

---

## 14. CI/CD Strategy

Automated tests will later be integrated with **GitHub Actions**.

The CI workflow will execute selected automated tests when appropriate repository events occur, such as code pushes or pull requests.

The pipeline will provide automated feedback about regression-test results.

---

## 15. Browser and Environment Strategy

Initial manual testing will be performed using a modern desktop web browser.

Primary automation execution will target Google Chrome.

Additional browser coverage may be considered as a future extension.

The project is not intended to provide exhaustive cross-browser or cross-device certification.

---

## 16. Reporting Strategy

Testing evidence will include:

* Test execution results
* Pass/fail status
* Defect reports
* Retest results
* Regression results
* Requirement traceability
* Automation reports
* CI execution results
* Summary QA metrics

The GitHub repository will contain selected reports and screenshots as portfolio evidence.

---

## 17. Traceability Strategy

Traceability will be maintained between:

Requirement
→ Test Scenario
→ Test Case
→ Test Execution
→ Defect
→ Automated Test

A Requirements Traceability Matrix will later summarize these relationships.

Stable identifiers will be used throughout the project.

Examples:

* `REQ-LOGIN-002`
* `TS-LOGIN-001`
* `TC-LOGIN-001`

---

## 18. Out-of-Scope Testing

The following testing activities are outside the initial project scope:

* Security penetration testing
* Load and stress testing
* Production infrastructure testing
* Real payment gateway certification
* Native mobile application testing
* Full accessibility certification
* Full visual-regression certification

These areas may be identified as future project extensions.

---

## 19. Strategy Review

The test strategy may be refined as:

* New functionality is discovered.
* Requirements are clarified.
* Risks change.
* Defects reveal additional areas requiring coverage.
* Automation feasibility becomes clearer.

Any significant change to the testing approach should be documented in the project artifacts.
