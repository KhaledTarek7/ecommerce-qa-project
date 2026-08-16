# Test Cases

## MOD-01 — Authentication / Login

---

### TC-LOGIN-001 — Successful login with valid credentials

**Related Requirement:** REQ-LOGIN-002
**Related Scenario:** TS-LOGIN-001
**Priority:** High
**Test Type:** Positive / Functional
**Status:** Not Run

**Preconditions:**

* SauceDemo login page is accessible.
* User is not already authenticated.

**Test Data:**

* Username: `standard_user`
* Password: `secret_sauce`

**Test Steps:**

1. Open `https://www.saucedemo.com/`.
2. Enter `standard_user` in the Username field.
3. Enter `secret_sauce` in the Password field.
4. Click the Login button.

**Expected Result:**

* Authentication succeeds.
* User is redirected to the product inventory page.
* Product listing is displayed.

---

### TC-LOGIN-002 — Login with invalid username

**Related Requirement:** REQ-LOGIN-003, REQ-LOGIN-006
**Related Scenario:** TS-LOGIN-002
**Priority:** High
**Test Type:** Negative / Functional
**Status:** Not Run

**Preconditions:**

* SauceDemo login page is accessible.

**Test Data:**

* Username: `invalid_user`
* Password: `secret_sauce`

**Test Steps:**

1. Open the SauceDemo login page.
2. Enter `invalid_user` in the Username field.
3. Enter `secret_sauce` in the Password field.
4. Click the Login button.

**Expected Result:**

* Authentication is rejected.
* User remains on the login page.
* An authentication error message is displayed.

---

### TC-LOGIN-003 — Login with invalid password

**Related Requirement:** REQ-LOGIN-003, REQ-LOGIN-006
**Related Scenario:** TS-LOGIN-003
**Priority:** High
**Test Type:** Negative / Functional
**Status:** Not Run

**Test Data:**

* Username: `standard_user`
* Password: `invalid_password`

**Test Steps:**

1. Open the SauceDemo login page.
2. Enter `standard_user` in the Username field.
3. Enter `invalid_password` in the Password field.
4. Click the Login button.

**Expected Result:**

* Authentication is rejected.
* User remains on the login page.
* An authentication error message is displayed.

---

### TC-LOGIN-004 — Login with invalid username and invalid password

**Related Requirement:** REQ-LOGIN-003, REQ-LOGIN-006
**Related Scenario:** TS-LOGIN-004
**Priority:** High
**Test Type:** Negative / Functional
**Status:** Not Run

**Test Data:**

* Username: `invalid_user`
* Password: `invalid_password`

**Test Steps:**

1. Open the SauceDemo login page.
2. Enter an invalid username.
3. Enter an invalid password.
4. Click the Login button.

**Expected Result:**

* Authentication is rejected.
* User remains on the login page.
* An authentication error message is displayed.

---

### TC-LOGIN-005 — Login with empty username

**Related Requirement:** REQ-LOGIN-004, REQ-LOGIN-006
**Related Scenario:** TS-LOGIN-005
**Priority:** High
**Test Type:** Negative / Validation
**Status:** Not Run

**Test Data:**

* Username: Empty
* Password: `secret_sauce`

**Test Steps:**

1. Open the SauceDemo login page.
2. Leave the Username field empty.
3. Enter `secret_sauce` in the Password field.
4. Click the Login button.

**Expected Result:**

* Authentication is prevented.
* User remains on the login page.
* A validation message indicates that the username is required.

---

### TC-LOGIN-006 — Login with empty password

**Related Requirement:** REQ-LOGIN-005, REQ-LOGIN-006
**Related Scenario:** TS-LOGIN-006
**Priority:** High
**Test Type:** Negative / Validation
**Status:** Not Run

**Test Data:**

* Username: `standard_user`
* Password: Empty

**Test Steps:**

1. Open the SauceDemo login page.
2. Enter `standard_user` in the Username field.
3. Leave the Password field empty.
4. Click the Login button.

**Expected Result:**

* Authentication is prevented.
* User remains on the login page.
* A validation message indicates that the password is required.

---

### TC-LOGIN-007 — Login with empty username and password

**Related Requirement:** REQ-LOGIN-004, REQ-LOGIN-005, REQ-LOGIN-006
**Related Scenario:** TS-LOGIN-007
**Priority:** High
**Test Type:** Negative / Validation
**Status:** Not Run

**Test Data:**

* Username: Empty
* Password: Empty

**Test Steps:**

1. Open the SauceDemo login page.
2. Leave the Username field empty.
3. Leave the Password field empty.
4. Click the Login button.

**Expected Result:**

* Authentication is prevented.
* User remains on the login page.
* A validation message is displayed for the missing required credential information.

---

### TC-LOGIN-008 — Login with locked-out user

**Related Requirement:** REQ-LOGIN-007
**Related Scenario:** TS-LOGIN-008
**Priority:** High
**Test Type:** Negative / Access Control
**Status:** Not Run

**Test Data:**

* Username: `locked_out_user`
* Password: `secret_sauce`

**Test Steps:**

1. Open the SauceDemo login page.
2. Enter `locked_out_user` in the Username field.
3. Enter `secret_sauce` in the Password field.
4. Click the Login button.

**Expected Result:**

* Authentication is rejected.
* User remains on the login page.
* The application indicates that the user is locked out.

---
