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
