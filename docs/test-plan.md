# Test Plan

## 1. Introduction

This Test Plan defines the scope, objectives, resources, environment, execution approach, entry and exit criteria, risks, and deliverables for testing the **SauceDemo / Swag Labs** web application.

The project is designed as an end-to-end Quality Assurance portfolio project demonstrating both manual and automated testing practices.

The initial testing phase will focus on manual functional validation before selected stable and high-value scenarios are automated.

---

## 2. Application Under Test

**Application:** SauceDemo / Swag Labs
**Application Type:** Web-based e-commerce demo application
**URL:** https://www.saucedemo.com/

The application provides a simplified e-commerce workflow including authentication, product browsing, cart management, checkout, order completion, and logout.

---

## 3. Test Objectives

The objectives of testing are to:

* Verify that documented functional requirements behave as expected.
* Validate critical customer workflows from login through order completion.
* Verify positive and negative application behavior.
* Validate input and error handling where applicable.
* Identify functional and usability defects.
* Verify consistency between modules during end-to-end workflows.
* Establish repeatable regression coverage.
* Maintain traceability between requirements, test cases, executions, and defects.
* Identify suitable scenarios for future automation.

---

## 4. In-Scope Functional Areas

The following modules are included in the project scope:

| Module ID | Functional Area                 |
| --------- | ------------------------------- |
| MOD-01    | Authentication / Login          |
| MOD-02    | Product Listing & Sorting       |
| MOD-03    | Product Details                 |
| MOD-04    | Shopping Cart                   |
| MOD-05    | Checkout — Customer Information |
| MOD-06    | Checkout — Order Overview       |
| MOD-07    | Order Completion                |
| MOD-08    | Navigation, Menu & Session      |

Testing will include individual module validation as well as end-to-end workflows involving multiple modules.

---

## 5. Out of Scope

The following areas are outside the initial project scope:

* User registration
* Product search
* Real payment gateway processing
* Production infrastructure testing
* Security penetration testing
* Load and stress testing
* Native mobile application testing
* Full accessibility certification
* Full visual-regression testing
* Real order fulfillment

Out-of-scope items may be identified as future project extensions but will not be included in the initial execution results.

---

## 6. Test Approach

Testing will follow the documented project Test Strategy.

The main execution sequence will be:

Requirements
→ Test Scenarios
→ Test Cases
→ Test Data
→ Manual Execution
→ Defect Reporting
→ Retesting
→ Regression Testing
→ Automation Candidate Selection
→ Automated Regression

Testing will primarily use a black-box, risk-based approach.

---

## 7. Test Types

The project will include:

* Functional testing
* Positive testing
* Negative testing
* Boundary and edge-case testing
* UI functional testing
* Workflow / end-to-end testing
* Smoke testing
* Sanity testing
* Regression testing
* Exploratory testing
* Automated regression testing

Not every test type will be applied to every module.

---

## 8. Test Environment

Initial testing will use the following environment:

| Component           | Test Environment            |
| ------------------- | --------------------------- |
| Application         | SauceDemo / Swag Labs       |
| Environment Type    | Public demo web environment |
| URL                 | https://www.saucedemo.com/  |
| Platform            | Desktop web                 |
| Primary Browser     | Google Chrome               |
| Internet Connection | Required                    |
| Automation Language | Python                      |
| UI Automation Tool  | Selenium WebDriver          |
| Test Framework      | pytest                      |
| BDD Framework       | Behave                      |
| Test Management     | Jira + Zephyr               |
| Source Control / CI | GitHub + GitHub Actions     |

Exact browser, operating-system, Python, Selenium, and dependency versions will be recorded when automation execution begins.

---

## 9. Test Data

The project will use controlled test data.

### Primary User

`standard_user`

This user will be used for baseline functional and end-to-end testing.

### Additional Test Personas

Additional predefined users may be used for targeted testing:

* `locked_out_user`
* `problem_user`
* `performance_glitch_user`
* `error_user`
* `visual_user`

### Checkout Data

Synthetic customer information will be used during checkout testing.

No real personal or production customer information will be required.

---

## 10. Entry Criteria

Manual functional test execution may begin when:

* The application is accessible.
* The primary test environment is available.
* Application modules have been identified.
* Derived requirements have been documented.
* Relevant test scenarios and test cases have been prepared.
* Required test accounts are available.
* Test data required for execution has been prepared.

Automation implementation may begin when:

* Relevant functionality has been manually tested.
* Expected behavior is sufficiently understood.
* Selected test cases are considered stable.
* Automation candidates have been identified.

---

## 11. Exit Criteria

The initial manual testing cycle may be considered complete when:

* All planned high-priority test cases have been executed.
* Critical end-to-end workflows have been validated.
* Test execution results have been recorded.
* Identified defects have been documented.
* Critical and high-severity defects have been reviewed.
* Failed tests requiring retesting have been addressed where possible.
* Requirement coverage has been reviewed.
* A regression set has been identified.
* Test summary metrics have been prepared.

Automation completion will be evaluated separately based on the selected automation scope.

---

## 12. Suspension Criteria

Testing may be suspended if:

* The application becomes unavailable.
* Authentication is unavailable for all usable test accounts.
* A blocker defect prevents access to major parts of the application.
* The test environment becomes unstable enough that results cannot be trusted.
* Required test data or dependencies are unavailable.

---

## 13. Resumption Criteria

Testing may resume when:

* Application access is restored.
* The blocking environment issue is resolved.
* A blocker defect has been fixed or an acceptable workaround is available.
* Test data or required dependencies become available.
* The environment is stable enough to produce reliable results.

---

## 14. Defect Management

Defects discovered during execution will be documented using Jira.

Each valid defect should include, where applicable:

* Defect title
* Description
* Environment
* Preconditions
* Steps to reproduce
* Actual result
* Expected result
* Severity
* Priority
* Evidence
* Related requirement
* Related test case
* Execution status

Defects discovered from Zephyr executions should be linked to the corresponding failed test execution where possible.

After a defect is reported as fixed, QA will perform retesting.

If the fix succeeds:

`Failed → Defect → Fixed → Retest → Pass`

If the defect remains reproducible:

`Failed → Defect → Fixed → Retest → Fail → Reopen`

---

## 15. Severity and Priority

Defects will be evaluated using both severity and priority.

### Severity

Severity represents the technical or functional impact of the defect.

Suggested levels:

* Critical
* High
* Medium
* Low

### Priority

Priority represents how urgently the defect should be addressed.

Suggested levels:

* Highest
* High
* Medium
* Low

Severity and priority are related but do not necessarily have the same value.

---

## 16. Test Deliverables

The project will produce the following QA deliverables:

### Documentation

* Application Overview
* Module Inventory
* Functional Requirements
* Test Strategy
* Test Plan
* Test Scenarios
* Test Cases
* Requirements Traceability Matrix

### Test Management

* Jira requirements / work items
* Zephyr test cases
* Zephyr test cycles
* Test execution records
* Jira defect reports
* Retest evidence

### Automation

* Selenium automation framework
* pytest test suite
* Page Object Model
* Fixtures
* Reusable utilities
* Test data
* Behave feature files
* Step definitions

### Reporting and DevOps

* Manual execution results
* Defect evidence
* Automation reports
* Test metrics
* GitHub Actions workflow
* CI execution evidence

---

## 17. Roles and Responsibilities

For this portfolio project, the QA Engineer / Project Owner is responsible for:

* Requirement analysis
* Test planning
* Test design
* Test-data preparation
* Manual execution
* Defect reporting
* Retesting
* Regression testing
* Automation implementation
* Test reporting
* Traceability
* Repository maintenance

In a real software-development project, these responsibilities would typically be distributed among QA Engineers, Developers, Business Analysts, Product Owners, DevOps Engineers, and other stakeholders.

---

## 18. Test Execution Phases

The project will be executed through the following phases:

### Phase 1 — Application Analysis

Understand the application and identify functional modules.

### Phase 2 — Requirement Analysis

Document derived functional requirements and assumptions.

### Phase 3 — Test Planning

Prepare the Test Strategy and Test Plan.

### Phase 4 — Test Design

Create test scenarios, detailed test cases, and test data.

### Phase 5 — Test Management Setup

Configure Jira and Zephyr and establish requirement-to-test traceability.

### Phase 6 — Manual Test Execution

Execute planned test cases and record results.

### Phase 7 — Defect Management

Report defects, link failures, retest fixes, and perform regression testing.

### Phase 8 — Automation

Implement selected regression coverage using Selenium, Python, and pytest.

### Phase 9 — BDD

Implement selected workflows using Behave and Gherkin.

### Phase 10 — CI/CD

Execute automated tests using GitHub Actions.

### Phase 11 — Reporting and Portfolio Finalization

Prepare metrics, reports, evidence, architecture diagrams, and final repository documentation.

---

## 19. Project Risks

| Risk                                                 | Impact                                                                  | Mitigation                                                                  |
| ---------------------------------------------------- | ----------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Public demo application behavior changes             | Existing requirements or tests may become outdated                      | Review application behavior before major execution cycles                   |
| Application becomes temporarily unavailable          | Test execution may be blocked                                           | Resume testing when environment becomes available                           |
| No formal business requirements are supplied         | Expected behavior may be ambiguous                                      | Clearly classify requirements as derived and document assumptions           |
| Demo personas intentionally exhibit unusual behavior | Intentional behavior may be incorrectly reported as a defect            | Compare behavior carefully and document evidence before classifying defects |
| UI changes break automated locators                  | Automated regression may fail even when business behavior remains valid | Use maintainable locators and Page Object Model                             |
| Excessive automation scope                           | Project becomes difficult to maintain                                   | Automate stable, high-value regression scenarios rather than every test     |
| Test data/state affects later execution              | Tests may become inconsistent                                           | Reset or control application state between relevant tests                   |

---

## 20. Test Completion Reporting

At the end of the execution cycle, a test summary will report metrics such as:

* Total test cases
* Executed test cases
* Passed test cases
* Failed test cases
* Blocked test cases
* Not-run test cases
* Pass percentage
* Defects identified
* Defects by severity
* Requirement coverage
* Automated regression coverage

The final GitHub portfolio will present selected evidence from these activities.
