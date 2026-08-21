# SauceDemo Exploratory Testing

## 1. Purpose

Exploratory testing supplements the scripted functional test suite by investigating application behavior without relying exclusively on predefined test steps.

The objective is to identify unexpected functional behavior, visual inconsistencies, usability concerns, workflow failures, and performance observations that may not be exposed through the existing scripted test cases.

---

## 2. Exploratory Testing Approach

Testing will use time-boxed exploratory charters focused primarily on SauceDemo's alternate test personas.

The standard functional baseline was executed primarily using:

`standard_user`

Exploratory testing will focus on:

- `problem_user`
- `error_user`
- `visual_user`
- `performance_glitch_user`

The `locked_out_user` behavior was already covered during Authentication testing.

Observations will first be recorded as findings.

A Jira Bug will only be created when an observation:

1. Can be reproduced.
2. Conflicts with expected application behavior.
3. Has sufficient evidence.
4. Can be described using clear reproduction steps.

---

# 3. Exploratory Charters

## EX-01 — Product and Cart Exploration using problem_user

### Objective

Explore product browsing, product details, cart behavior, and checkout using `problem_user`.

### Test Data

Username:

`problem_user`

Password:

`secret_sauce`

### Focus Areas

- Product information consistency
- Product images
- Product-detail navigation
- Add / Remove behavior
- Shopping-cart contents
- Product state consistency
- Checkout behavior
- Unexpected product changes

### Timebox

20 minutes

---

## EX-02 — Functional Error Exploration using error_user

### Objective

Explore critical purchasing functionality using `error_user` and identify operations that behave differently from the established standard-user baseline.

### Test Data

Username:

`error_user`

Password:

`secret_sauce`

### Focus Areas

- Product interaction
- Cart modification
- Checkout customer information
- Checkout progression
- Error handling
- Order completion
- Navigation behavior

### Timebox

20 minutes

---

## EX-03 — Visual Exploration using visual_user

### Objective

Inspect the application for visual and presentation inconsistencies while using `visual_user`.

### Test Data

Username:

`visual_user`

Password:

`secret_sauce`

### Focus Areas

- Product images
- Product names
- Button alignment
- Layout
- Labels
- Cart presentation
- Checkout presentation
- Navigation controls
- Visual consistency between pages

### Timebox

15 minutes

---

## EX-04 — Performance Exploration using performance_glitch_user

### Objective

Explore application response behavior using `performance_glitch_user`.

### Test Data

Username:

`performance_glitch_user`

Password:

`secret_sauce`

### Focus Areas

- Login response time
- Products page loading
- Product-details navigation
- Shopping-cart navigation
- Checkout transitions
- User-perceived delays
- Functional behavior following delays

### Timebox

15 minutes

---

# 4. Observation Classification

Each observation should initially be classified as:

- Expected Behavior
- Potential Functional Defect
- Potential Visual Defect
- Potential Performance Issue
- Usability Observation
- Requires Further Investigation

An observation should not automatically be classified as a defect.

---

# 5. Exploratory Observation Log

| Observation ID | Charter | Observation | Expected Behavior | Actual Behavior | Classification | Reproducible | Evidence | Jira Bug |
|---|---|---|---|---|---|---|---|---|
| OBS-001 | | | | | | | | |

---

# 6. Defect Qualification

Before creating a Jira Bug, the observation should be reproduced and compared with the established functional baseline.

A confirmed defect should include:

- Clear Summary
- Environment
- Preconditions
- Reproduction Steps
- Expected Result
- Actual Result
- Severity
- Priority
- Evidence
- Related requirement or functional area
