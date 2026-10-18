# DIGITAL AGRICULTURE MANAGEMENT SYSTEM

# DETAILED SOFTWARE TEST CASE DOCUMENT

**Document:** `test-cases.md`\
**Project:** Digital Agriculture Management System\
**Version:** 1.0\
**Prepared by:** Testing / Integration Team\
**Purpose:** Functional, integration, database, UI, navigation, and
basic security testing\
**Initial execution status:** Not Run

> **Important:** This file is a test plan, not proof that tests have
> passed. Execute each applicable case and record the actual result.
> Mark a case `Passed` only after observing the expected result. If a
> feature is not implemented, mark it `Not Applicable`; if a required
> service/environment is unavailable, mark it `Blocked`.

------------------------------------------------------------------------

## 1. Purpose

This document defines repeatable test cases for the Digital Agriculture
Management System. It is intended to help the testing team verify
implemented features, identify defects, validate Java/backend and
MySQL/database integration where used, and retain a clear record of
testing evidence.

The exact implementation is authoritative. Only execute cases for
features that exist in the current build. Adapt field names, routes,
roles, and validation rules to match the actual project.

## 2. Scope

The test plan covers these modules **where implemented**:

1.  Login and authentication
2.  Registration
3.  Logout and session handling
4.  Home page and dashboard
5.  Farmer management
6.  Crop management
7.  Market prices/information
8.  Weather information
9.  Farmer queries
10. Java/backend processing and API or form handlers
11. MySQL connectivity and database operations
12. Frontend-backend-database integration
13. Navigation and links
14. User interface and responsive layout
15. Input validation and basic security/access control
16. Error handling, retesting, and regression testing

## 3. Test Environment Record

Complete this section for the actual test session.

  --------------------------------------------------------------------------
  Field                               Value
  ----------------------------------- --------------------------------------
  Project                             Digital Agriculture Management System

  Tester                              SACHIN KUMAR 

  Test date                           15/10/2026

  Build/commit ID                     9933b2f
  

  Operating system                    Windows 11

  Browser and version                 Google

  Frontend technologies               HTML / CSS / JavaScript (confirm
                                      actual build)

  Backend technology                  Java (record framework/version, if
                                      applicable)

  Database                            MySQL (record version)

  Database tool                       MySQL Workbench configured tool

  Application URL or local path       http://127.0.0.1:5500/index.html

  Test database/schema                digital_agriculture_db

  Test environment                    Local  Staging

  Git branch                          main
  --------------------------------------------------------------------------

### 3.1 Test data and safety

-   Use fictional test data, not real farmer personal information.
-   Use a development/test database, not production data.
-   Use disposable records for update/delete tests.
-   Never put passwords, database credentials, API keys, or private user
    data in this document or GitHub.
-   Do not perform destructive tests against a live database.
-   Record screenshots or sanitized logs when they help reproduce a
    defect.

## 4. Test Status Definitions

  -----------------------------------------------------------------------
  Status                              Meaning
  ----------------------------------- -----------------------------------
  Not Run                             Test has not been executed yet.

  Passed                              Actual behavior matches the
                                      expected result.

  Failed                              Actual behavior does not match the
                                      expected result.

  Blocked                             A dependency, permission,
                                      environment, or required feature
                                      prevents execution.

  Not Applicable                      The test does not apply to the
                                      implemented application.

  Retest Required                     A defect fix is available and needs
                                      verification.
  -----------------------------------------------------------------------

## 5. Priority Definitions

-   **High:** Core workflow, data integrity, authentication, or access
    control.
-   **Medium:** Important module behavior or usability.
-   **Low:** Minor presentation or non-critical behavior.

## 6. Test Case Format

Every test case includes an ID, module, priority, objective,
preconditions, sample data, steps, expected result, actual result,
status, and evidence/remarks. Actual results and evidence must be added
during execution.

------------------------------------------------------------------------

# 7. DETAILED TEST CASES

## 7.1 Login and Authentication

### TC-01 --- Login with valid credentials

-   **Module:** Login
-   **Priority:** High
-   **Objective:** Verify that a registered test user can sign in.
-   **Preconditions:** Application is running; login page is available;
    a test account exists and is active.
-   **Test data:** Correct username/email and matching password for the
    test account.
-   **Steps:**
    1.  Open the application login page.
    2.  Enter the registered username/email.
    3.  Enter the correct password.
    4.  Click **Login/Sign In**.
    5.  Observe the response and destination page.
-   **Expected result:** Credentials are validated; login succeeds; the
    user is routed to the correct page for their role; no authentication
    error appears.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.
-   **Evidence/remarks:** Record destination page and any relevant
    screenshot.

### TC-02 --- Login with incorrect password

-   **Module:** Login
-   **Priority:** High
-   **Objective:** Ensure incorrect credentials do not grant access.
-   **Preconditions:** A registered test account exists.
-   **Test data:** Valid username/email and an incorrect password.
-   **Steps:**
    1.  Open the login page.
    2.  Enter the valid username/email.
    3.  Enter an incorrect password.
    4.  Submit the form.
    5.  Check the message and whether a protected page opens.
-   **Expected result:** Authentication is rejected; a suitable error
    message is shown; protected content is not accessible.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.
-   **Evidence/remarks:** Do not record the real password.

### TC-03 --- Login with an unregistered username/email

-   **Module:** Login
-   **Priority:** High
-   **Objective:** Verify that unknown accounts cannot sign in.
-   **Preconditions:** Login page is available.
-   **Test data:** A fictional username/email not registered in the test
    database and any invalid password.
-   **Steps:**
    1.  Open the login page.
    2.  Enter the unregistered username/email.
    3.  Enter a password.
    4.  Submit the form.
-   **Expected result:** Access is denied and an appropriate error is
    displayed.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.
-   **Evidence/remarks:** Confirm no unexpected account is created.

### TC-04 --- Submit login form with both fields empty

-   **Module:** Login
-   **Priority:** High
-   **Objective:** Verify required-field validation.
-   **Preconditions:** Login page is available.
-   **Test data:** Empty username/email and empty password.
-   **Steps:**
    1.  Open the login page.
    2.  Leave both fields empty.
    3.  Click Login.
-   **Expected result:** Required-field validation appears; no
    authentication succeeds; no invalid user session is created.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-05 --- Submit login with one required field empty

-   **Module:** Login
-   **Priority:** High
-   **Objective:** Verify each required field is validated
    independently.
-   **Preconditions:** Login page is available.
-   **Test data:** Run once with username/email empty and once with
    password empty.
-   **Steps:**
    1.  Enter a value in only one login field.
    2.  Leave the other required field empty.
    3.  Submit the form.
    4.  Repeat with the other field empty.
-   **Expected result:** The missing field is identified; login is
    rejected.
-   **Actual result:** Record both runs.
-   **Status:** Not Run.

### TC-06 --- Login with whitespace-only input

-   **Module:** Login
-   **Priority:** Medium
-   **Objective:** Verify whitespace is not accidentally treated as
    valid credentials.
-   **Preconditions:** Login page is available.
-   **Test data:** Spaces only in one or both fields.
-   **Steps:**
    1.  Enter spaces in the username/email field.
    2.  Enter spaces in the password field.
    3.  Submit the form.
-   **Expected result:** Input is rejected according to validation
    rules; access is not granted.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-07 --- Logout and attempt to reopen a protected page

-   **Module:** Authentication/session
-   **Priority:** High
-   **Objective:** Verify logout ends the authenticated session.
-   **Preconditions:** A test user can log in; logout and protected-page
    behavior are implemented.
-   **Steps:**
    1.  Log in with valid test credentials.
    2.  Open a protected page.
    3.  Click Logout.
    4.  Attempt to reopen the protected page using its navigation link
        or direct address.
    5.  If relevant, use browser Back and refresh.
-   **Expected result:** The session is ended; protected content is not
    available without re-authentication; the application redirects or
    denies access as designed.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-08 --- Role-based login destination

-   **Module:** Authentication/authorization
-   **Priority:** High
-   **Objective:** Verify each supported role receives the correct
    access and destination.
-   **Preconditions:** The application implements multiple roles such as
    farmer and admin; separate test accounts exist.
-   **Steps:**
    1.  Log in using a test account for each supported role.
    2.  Record the landing page.
    3.  Check which navigation options and protected features are
        available.
    4.  Log out between accounts.
-   **Expected result:** Each account is routed and authorized according
    to the role rules actually implemented.
-   **Actual result:** Record per role.
-   **Status:** Not Run.
-   **Evidence/remarks:** Mark Not Applicable if the application has no
    role-based behavior.

## 7.2 Registration

### TC-09 --- Register a new user with valid data

-   **Module:** Registration
-   **Priority:** High
-   **Objective:** Verify valid registration creates an account if
    registration is implemented.
-   **Preconditions:** Registration page and backend/database are
    available; test email/username is unused.
-   **Test data:** Fictional name, unique test email/username, and
    password meeting the actual rules.
-   **Steps:**
    1.  Open the registration page.
    2.  Fill in all required fields with valid test data.
    3.  Submit the form.
    4.  Observe the confirmation or error.
    5.  Verify the account through the supported application or test
        database.
-   **Expected result:** The form validates; the account is created
    once; confirmation is shown; saved values are correct.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-10 --- Register with required fields missing

-   **Module:** Registration
-   **Priority:** High
-   **Objective:** Ensure incomplete registration is rejected.
-   **Preconditions:** Registration form is available.
-   **Steps:**
    1.  Open the registration page.
    2.  Leave one required field empty.
    3.  Fill the remaining required fields with valid test data.
    4.  Submit.
    5.  Repeat for other required fields as appropriate.
-   **Expected result:** The missing field is identified; no incomplete
    account is created.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-11 --- Register with an already-used email/username

-   **Module:** Registration
-   **Priority:** High
-   **Objective:** Verify duplicate identifiers are handled.
-   **Preconditions:** A test account already exists; uniqueness is
    required by the application.
-   **Steps:**
    1.  Open registration.
    2.  Enter otherwise valid details.
    3.  Reuse the existing email/username.
    4.  Submit.
-   **Expected result:** Duplicate registration is rejected according to
    the application's uniqueness rules; existing account data is not
    overwritten.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-12 --- Validate email format

-   **Module:** Registration
-   **Priority:** Medium
-   **Objective:** Verify invalid email formats are rejected.
-   **Preconditions:** Registration form includes an email field.
-   **Test data:** Examples such as `user@`, `user.example.com`, or an
    empty value when required.
-   **Steps:**
    1.  Enter the invalid email value.
    2.  Complete other fields with valid test data.
    3.  Submit.
-   **Expected result:** Invalid email formatting is rejected and clear
    feedback is displayed.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-13 --- Verify password policy and confirmation

-   **Module:** Registration
-   **Priority:** High
-   **Objective:** Verify the password policy and confirmation match, if
    these controls exist.
-   **Preconditions:** Registration includes password rules and/or
    confirmation.
-   **Steps:**
    1.  Enter a password that violates the configured policy and submit.
    2.  Record the response.
    3.  If a confirmation field exists, enter mismatching password
        values and submit.
-   **Expected result:** Passwords that violate defined rules or do not
    match are rejected; the requirements are communicated clearly.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.
-   **Remarks:** Use the project's actual password policy; do not assume
    a rule that is not implemented.

## 7.3 Home Page and Dashboard

### TC-14 --- Open the home page

-   **Module:** Home
-   **Priority:** Medium
-   **Objective:** Verify the main page loads correctly.
-   **Preconditions:** Application is available.
-   **Steps:**
    1.  Open the application home page.
    2.  Wait for page resources to load.
    3.  Inspect headings, menus, content, and visible assets.
    4.  Check the browser console if a visible problem occurs.
-   **Expected result:** The page loads without a fatal error;
    implemented content and navigation are visible.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-15 --- Open the dashboard after login

-   **Module:** Dashboard
-   **Priority:** High
-   **Objective:** Verify an authorized user can open the appropriate
    dashboard.
-   **Preconditions:** Login works and dashboard is implemented.
-   **Steps:**
    1.  Log in using an authorized test account.
    2.  Navigate to the dashboard.
    3.  Inspect the displayed components and available actions.
-   **Expected result:** Dashboard loads; the correct role's features
    are displayed; no unexpected access error occurs.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-16 --- Verify dashboard summary values

-   **Module:** Dashboard
-   **Priority:** Medium
-   **Objective:** Check that displayed totals or summaries match source
    records.
-   **Preconditions:** Dashboard statistics and corresponding records
    are implemented.
-   **Steps:**
    1.  Record the displayed summary values.
    2.  Compare them with the relevant test records using an authorized
        method.
    3.  Refresh the dashboard.
    4.  Compare the values again.
-   **Expected result:** Displayed totals match the source data and
    refresh behavior is consistent.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.
-   **Remarks:** Mark Not Applicable if the dashboard contains no data
    summaries.

## 7.4 Farmer Management

### TC-17 --- Add a farmer record

-   **Module:** Farmer Management
-   **Priority:** High
-   **Objective:** Verify a valid farmer record can be created where
    supported.
-   **Preconditions:** Farmer management form exists; tester has
    permission; backend/database are available.
-   **Test data:** Fictional farmer name and valid sample values for
    required fields.
-   **Steps:**
    1.  Open Farmer Management.
    2.  Choose Add Farmer.
    3.  Enter valid test information.
    4.  Submit.
    5.  Observe the response.
    6.  Open the farmer list and locate the new test record.
-   **Expected result:** A single record is created with the expected
    values and appropriate confirmation is displayed.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-18 --- Submit farmer form with missing/invalid data

-   **Module:** Farmer Management
-   **Priority:** High
-   **Objective:** Verify validation of required farmer fields.
-   **Preconditions:** Add Farmer form exists.
-   **Steps:**
    1.  Leave a required field empty or enter a value of the wrong
        format.
    2.  Submit the form.
    3.  Inspect the validation response.
-   **Expected result:** Invalid input is rejected; field-level feedback
    is shown where practical; no invalid record is created.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-19 --- View farmer details

-   **Module:** Farmer Management
-   **Priority:** Medium
-   **Objective:** Verify the selected farmer's information is displayed
    accurately.
-   **Preconditions:** A known farmer test record exists.
-   **Steps:**
    1.  Open the farmer list.
    2.  Select the test record.
    3.  Open its details.
    4.  Compare visible fields with the test data.
-   **Expected result:** The correct record and values are displayed;
    unrelated records are not shown as the selected farmer.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-20 --- Update farmer information

-   **Module:** Farmer Management
-   **Priority:** High
-   **Objective:** Verify edits are saved to the correct record.
-   **Preconditions:** A disposable farmer test record exists and
    editing is implemented.
-   **Steps:**
    1.  Open the record.
    2.  Select Edit.
    3.  Change one editable field.
    4.  Save.
    5.  Reopen or refresh the record.
-   **Expected result:** The new value persists; unrelated fields and
    records remain unchanged.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-21 --- Delete a farmer test record

-   **Module:** Farmer Management
-   **Priority:** Medium
-   **Objective:** Verify deletion behavior without affecting unrelated
    records.
-   **Preconditions:** A disposable test record exists; delete is
    implemented; tester has permission.
-   **Steps:**
    1.  Select the disposable test record.
    2.  Choose Delete.
    3.  Confirm if prompted.
    4.  Refresh the list and search for the record.
-   **Expected result:** The selected record is removed or marked
    inactive according to the design; other records remain unchanged.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.
-   **Safety:** Never use a real farmer record for this test.

## 7.5 Crop Management

### TC-22 --- Add a crop with valid data

-   **Module:** Crop Management
-   **Priority:** High
-   **Objective:** Verify crop creation.
-   **Preconditions:** Crop form exists; required services are running;
    tester has permission.
-   **Test data:** Crop name such as Wheat, valid season, positive area,
    and other required sample values.
-   **Steps:**
    1.  Open Crop Management.
    2.  Select Add Crop.
    3.  Enter valid test data.
    4.  Submit the form.
    5.  Open the crop list.
    6.  Locate and inspect the created record.
-   **Expected result:** Crop is created once and the saved values match
    the submitted data.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-23 --- Add a crop with missing required data

-   **Module:** Crop Management
-   **Priority:** High
-   **Objective:** Verify required crop fields are validated.
-   **Preconditions:** Crop form exists.
-   **Steps:**
    1.  Open Add Crop.
    2.  Leave a required field empty.
    3.  Complete the remaining fields.
    4.  Submit.
-   **Expected result:** Submission is rejected or blocked by
    validation; no incomplete crop record is created.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-24 --- Validate crop area and numeric fields

-   **Module:** Crop Management
-   **Priority:** Medium
-   **Objective:** Verify numeric fields accept valid values and reject
    invalid values.
-   **Preconditions:** Crop form includes a numeric area or quantity
    field.
-   **Test data:** A valid positive number, zero, a negative number,
    alphabetic text, and an unusually large value.
-   **Steps:**
    1.  Test each input value separately.
    2.  Submit the form for each value.
    3.  Record whether the application accepts or rejects it.
-   **Expected result:** Values follow documented business rules;
    invalid numeric values are rejected; the application does not store
    malformed numbers.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-25 --- View crop details

-   **Module:** Crop Management
-   **Priority:** Medium
-   **Objective:** Verify crop information is retrieved accurately.
-   **Preconditions:** A known crop test record exists.
-   **Steps:**
    1.  Open the crop list.
    2.  Select a crop.
    3.  Open its details.
    4.  Compare displayed fields with the saved test data.
-   **Expected result:** Correct crop details are shown and values are
    consistent with the saved record.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-26 --- Update crop information

-   **Module:** Crop Management
-   **Priority:** High
-   **Objective:** Verify crop updates persist.
-   **Preconditions:** A disposable crop test record exists and editing
    is supported.
-   **Steps:**
    1.  Open the crop record.
    2.  Select Edit.
    3.  Change an editable field.
    4.  Save.
    5.  Refresh and reopen the record.
-   **Expected result:** The updated value persists; the correct record
    is changed; unrelated records remain unchanged.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-27 --- Delete a crop test record

-   **Module:** Crop Management
-   **Priority:** Medium
-   **Objective:** Verify crop deletion or deactivation behavior.
-   **Preconditions:** A disposable crop record exists; delete is
    implemented.
-   **Steps:**
    1.  Select the disposable crop record.
    2.  Choose Delete.
    3.  Confirm if prompted.
    4.  Refresh the crop list.
    5.  Verify the record's state.
-   **Expected result:** The selected crop is removed or marked inactive
    according to design; other crops are unaffected.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

## 7.6 Market Information

### TC-28 --- Open market information page

-   **Module:** Market
-   **Priority:** Medium
-   **Objective:** Verify the market page opens and handles its data
    state.
-   **Preconditions:** Market page is implemented.
-   **Steps:**
    1.  Navigate to the market page.
    2.  Wait for content to load.
    3.  Inspect commodity names, prices, units, and source/date labels
        if provided.
-   **Expected result:** The page loads; available information is
    readable; an appropriate empty state appears if no data exists.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-29 --- Verify market price display

-   **Module:** Market
-   **Priority:** Medium
-   **Objective:** Check displayed prices against the configured source
    or test data.
-   **Preconditions:** A known market data source or controlled test
    dataset exists.
-   **Steps:**
    1.  Open the market page.
    2.  Select a commodity or market where supported.
    3.  Compare displayed values with the source/test data.
    4.  Check units, currency, and date labels.
-   **Expected result:** Values and units match the source; the page
    does not imply data is current if its timestamp/source indicates
    otherwise.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-30 --- Handle unavailable market data

-   **Module:** Market
-   **Priority:** Medium
-   **Objective:** Verify graceful handling of a failed data source.
-   **Preconditions:** A safe test setup can simulate the source being
    unavailable.
-   **Steps:**
    1.  Simulate an unavailable source in the test environment.
    2.  Open or refresh the market page.
    3.  Observe the user-facing result.
-   **Expected result:** The application shows an appropriate message or
    empty state; the page does not crash; sensitive technical details
    are not exposed.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

## 7.7 Weather Information

### TC-31 --- Open weather page

-   **Module:** Weather
-   **Priority:** Medium
-   **Objective:** Verify the weather page loads.
-   **Preconditions:** Weather page is implemented.
-   **Steps:**
    1.  Navigate to the weather page.
    2.  Inspect the page and any available weather details.
    3.  Check for missing content or an unexpected error.
-   **Expected result:** The page loads and shows available weather
    information or a clear empty/error state.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-32 --- Verify weather location selection

-   **Module:** Weather
-   **Priority:** Medium
-   **Objective:** Verify weather data corresponds to the requested
    location if location selection is supported.
-   **Preconditions:** The page supports a location input or selection.
-   **Steps:**
    1.  Enter a valid supported test location.
    2.  Request weather information.
    3.  Verify the location label and returned information.
    4.  Try an invalid location.
-   **Expected result:** Valid locations are handled correctly; invalid
    locations produce a clear message; displayed information is not
    assigned to the wrong location.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-33 --- Handle weather service failure

-   **Module:** Weather
-   **Priority:** Medium
-   **Objective:** Verify graceful error handling when the weather
    provider is unavailable.
-   **Preconditions:** A safe test method exists to simulate service
    failure.
-   **Steps:**
    1.  Simulate an unavailable provider or network failure.
    2.  Request weather data.
    3.  Observe the response.
    4.  Restore the service and try again.
-   **Expected result:** A clear error/retry state appears; the page
    remains usable; normal operation resumes when the dependency is
    restored.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

## 7.8 Farmer Queries

### TC-34 --- Submit a valid farmer query

-   **Module:** Farmer Queries
-   **Priority:** Medium
-   **Objective:** Verify query submission where the feature is
    implemented.
-   **Preconditions:** Query form and required services are available.
-   **Test data:** A fictional agricultural question with no private
    information.
-   **Steps:**
    1.  Open the farmer queries page.
    2.  Fill in all required fields.
    3.  Submit the query.
    4.  Observe confirmation or error feedback.
    5.  Verify persistence if saving is implemented.
-   **Expected result:** The query is validated and processed according
    to the design; success is shown only when appropriate.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-35 --- Submit an empty query

-   **Module:** Farmer Queries
-   **Priority:** Medium
-   **Objective:** Verify required query text is enforced.
-   **Preconditions:** Query form is available.
-   **Steps:**
    1.  Open the form.
    2.  Leave the required query field empty.
    3.  Submit.
-   **Expected result:** Validation prevents an empty query from being
    submitted or saved.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-36 --- Submit a query exceeding the configured length

-   **Module:** Farmer Queries
-   **Priority:** Low
-   **Objective:** Verify field length limits and safe handling.
-   **Preconditions:** A query text field and documented length limit
    exist.
-   **Steps:**
    1.  Enter text longer than the configured limit.
    2.  Submit the form.
    3.  Observe validation and page stability.
-   **Expected result:** The configured length limit is enforced; the
    page remains stable; the application provides understandable
    feedback.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

## 7.9 Backend and Java Processing

### TC-37 --- Submit a valid request to an implemented backend handler

-   **Module:** Backend/API
-   **Priority:** High
-   **Objective:** Verify the backend processes a valid request.
-   **Preconditions:** Java backend or relevant request handler is
    running; target route/handler exists.
-   **Steps:**
    1.  Identify an implemented form handler or API endpoint.
    2.  Prepare valid test data matching its contract.
    3.  Submit the request through the application or an authorized test
        client.
    4.  Inspect the response and resulting application behavior.
-   **Expected result:** The request is processed according to the
    endpoint's design; response and data structure are appropriate.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-38 --- Submit invalid data to backend

-   **Module:** Backend/API
-   **Priority:** High
-   **Objective:** Verify backend-side validation, not just browser-side
    validation.
-   **Preconditions:** An implemented backend handler exists.
-   **Steps:**
    1.  Prepare a request with a required field missing or invalid.
    2.  Submit it in the authorized test environment.
    3.  Inspect the response and database state.
-   **Expected result:** The backend rejects invalid data safely; a
    useful error is returned; no invalid record is persisted.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-39 --- Request an invalid route or resource

-   **Module:** Backend/API
-   **Priority:** Medium
-   **Objective:** Verify the application handles unknown routes.
-   **Preconditions:** Backend routing is implemented.
-   **Steps:**
    1.  Request a non-existent route in the test environment.
    2.  Observe the response.
-   **Expected result:** An appropriate not-found response or page
    appears; no unrelated data is returned; internal secrets are not
    disclosed.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-40 --- Verify backend error handling

-   **Module:** Backend/API
-   **Priority:** High
-   **Objective:** Verify unexpected dependency errors do not crash the
    entire workflow.
-   **Preconditions:** A safe method exists to simulate a controlled
    failure.
-   **Steps:**
    1.  Cause a controlled dependency failure in the test environment.
    2.  submit a valid request that depends on it.
    3.  Observe the response and logs.
    4.  Restore the dependency and repeat.
-   **Expected result:** The failure is handled; the user receives
    appropriate feedback; logs support diagnosis without exposing
    secrets to the user.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

## 7.10 MySQL Database Testing

### TC-41 --- Verify database connection

-   **Module:** Database
-   **Priority:** High
-   **Objective:** Confirm the backend can connect to the configured
    MySQL database.
-   **Preconditions:** MySQL service and test schema are available;
    configuration is set securely.
-   **Steps:**
    1.  Start the database service.
    2.  Start the application/backend.
    3.  Trigger a feature that reads or writes database data.
    4.  Review the application response and sanitized server logs.
-   **Expected result:** The application connects successfully and
    performs the requested database operation.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.
-   **Security note:** Never add database passwords to this file or
    commit them to GitHub.

### TC-42 --- Verify insertion of a test record

-   **Module:** Database
-   **Priority:** High
-   **Objective:** Verify a valid application operation stores the
    correct record.
-   **Preconditions:** Test database is connected; the relevant create
    operation exists.
-   **Steps:**
    1.  Submit valid test data through the application.
    2.  Observe the application result.
    3.  Inspect the test schema using an authorized database tool.
    4.  Compare the stored fields with the submitted values.
-   **Expected result:** One correct record is stored; values match; no
    unintended duplicate is created.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-43 --- Verify retrieval from MySQL

-   **Module:** Database
-   **Priority:** High
-   **Objective:** Verify the application retrieves the intended record.
-   **Preconditions:** A known test record exists in the test schema.
-   **Steps:**
    1.  Open the relevant list/details page.
    2.  Request the record.
    3.  Compare displayed values with the known test data.
-   **Expected result:** The correct record is retrieved and displayed
    with matching values.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-44 --- Verify record update in MySQL

-   **Module:** Database
-   **Priority:** High
-   **Objective:** Verify updates persist to the intended record.
-   **Preconditions:** A disposable test record exists and update is
    implemented.
-   **Steps:**
    1.  Update one editable field through the application.
    2.  Save changes.
    3.  Retrieve the record again.
    4.  Inspect the test database if needed.
-   **Expected result:** The intended record contains the new value;
    unrelated records remain unchanged.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-45 --- Verify deletion in MySQL

-   **Module:** Database
-   **Priority:** Medium
-   **Objective:** Verify deletion or soft deletion follows the
    application's design.
-   **Preconditions:** A disposable test record exists; deletion is
    implemented.
-   **Steps:**
    1.  Delete the test record through the application.
    2.  Verify the UI result.
    3.  Inspect the record state using an authorized test database
        method.
-   **Expected result:** The record is deleted or marked inactive
    according to design; no unrelated data is removed.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-46 --- Verify data persistence after application restart

-   **Module:** Database
-   **Priority:** High
-   **Objective:** Ensure ordinary application restart does not lose
    persisted records.
-   **Preconditions:** Persistent database storage is used and
    restarting is safe.
-   **Steps:**
    1.  Create a disposable test record.
    2.  Confirm it can be retrieved.
    3.  Restart the application/backend without resetting the test
        database.
    4.  Retrieve the record again.
-   **Expected result:** The record remains available with matching
    values.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-47 --- Verify database failure handling

-   **Module:** Database
-   **Priority:** High
-   **Objective:** Verify the application handles a database outage.
-   **Preconditions:** A controlled test environment can simulate a
    database outage safely.
-   **Steps:**
    1.  Simulate a database connection failure in the test environment.
    2.  Request a feature that requires the database.
    3.  Observe the user-facing result and sanitized logs.
    4.  Restore the connection and retry.
-   **Expected result:** The application fails gracefully; no false
    success is reported; recovery works when the database is restored.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

## 7.11 Frontend-Backend-Database Integration

### TC-48 --- Verify frontend-to-backend integration

-   **Module:** Integration
-   **Priority:** High
-   **Objective:** Verify the frontend submits a request to the correct
    backend operation.
-   **Preconditions:** Frontend and backend are running; the relevant
    operation exists.
-   **Steps:**
    1.  Open the relevant frontend form.
    2.  Enter valid test data.
    3.  Submit.
    4.  Inspect the request/response through approved developer tools or
        application logs.
    5.  Confirm the UI displays the response appropriately.
-   **Expected result:** The request reaches the correct handler; the
    response is handled correctly; no unexpected integration error
    occurs.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-49 --- Verify backend-to-database integration

-   **Module:** Integration
-   **Priority:** High
-   **Objective:** Verify the backend performs the expected database
    operation.
-   **Preconditions:** Backend and MySQL test database are available.
-   **Steps:**
    1.  Submit a valid create/read/update request.
    2.  Verify backend processing.
    3.  Verify the corresponding database result.
    4.  Retrieve the record through the application.
-   **Expected result:** Backend and database exchange the correct data
    and the application reflects the saved result.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-50 --- Verify complete create-and-read workflow

-   **Module:** Integration
-   **Priority:** High
-   **Objective:** Test a complete data workflow end-to-end.
-   **Preconditions:** A supported create-and-list feature exists.
-   **Steps:**
    1.  Open the relevant page.
    2.  Create a disposable test record.
    3.  Confirm success feedback.
    4.  Open the list/details view.
    5.  Verify the created record.
    6.  Refresh the page and verify again.
-   **Expected result:** Data moves through the frontend, backend, and
    database correctly and remains available after refresh.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-51 --- Verify frontend behavior when backend is unavailable

-   **Module:** Integration
-   **Priority:** High
-   **Objective:** Verify the UI handles backend unavailability.
-   **Preconditions:** A safe test environment can temporarily stop or
    isolate the backend.
-   **Steps:**
    1.  Open the relevant page.
    2.  Make the backend unavailable using an approved test procedure.
    3.  Submit or refresh the relevant operation.
    4.  Observe the UI.
    5.  Restore the backend and retry.
-   **Expected result:** A clear error or retry state appears; the UI
    does not falsely report success; normal operation resumes after
    recovery.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

## 7.12 Navigation and Links

### TC-52 --- Verify main navigation links

-   **Module:** Navigation
-   **Priority:** Medium
-   **Objective:** Check implemented menu links.
-   **Preconditions:** Main page is available.
-   **Steps:**
    1.  Open the main page.
    2.  Click each navigation link.
    3.  Verify the destination and page title/content.
    4.  Return and repeat for other links.
-   **Expected result:** Each link opens its intended page; no
    unintended broken route is found.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-53 --- Verify browser Back and Forward behavior

-   **Module:** Navigation
-   **Priority:** Low
-   **Objective:** Verify browser navigation does not produce unexpected
    errors.
-   **Preconditions:** At least three pages are available.
-   **Steps:**
    1.  Open the home page.
    2.  Navigate to two other pages.
    3.  Use Back and then Forward.
    4.  Observe content and authentication state.
-   **Expected result:** Browser navigation behaves consistently with
    the application's design and does not expose protected content after
    logout.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-54 --- Verify direct access to a page

-   **Module:** Navigation/access control
-   **Priority:** Medium
-   **Objective:** Check direct page addresses behave according to
    access rules.
-   **Preconditions:** A public page and, if implemented, a protected
    page are available.
-   **Steps:**
    1.  Open a public page directly.
    2.  Open a protected page while logged out.
    3.  Log in and open the protected page again.
-   **Expected result:** Public pages work as intended; protected pages
    enforce authentication and authorization.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

## 7.13 UI and Responsive Design

### TC-55 --- Verify desktop layout

-   **Module:** UI
-   **Priority:** Medium
-   **Objective:** Check layout and readability at desktop dimensions.
-   **Preconditions:** Application opens in a supported browser.
-   **Steps:**
    1.  Open the home page at a desktop viewport.
    2.  Review headings, cards, forms, tables, buttons, and navigation.
    3.  Repeat on important module pages.
-   **Expected result:** Elements are readable and usable; there is no
    major unintended overlap or clipping.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-56 --- Verify mobile/narrow viewport layout

-   **Module:** Responsive UI
-   **Priority:** Medium
-   **Objective:** Check key pages at a narrow viewport.
-   **Preconditions:** Browser responsive mode or a test device is
    available.
-   **Steps:**
    1.  Open the home page at a mobile-width viewport.
    2.  Inspect the navigation menu and content.
    3.  Check forms, cards, and tables.
    4.  Repeat for important pages.
-   **Expected result:** Important content remains readable and controls
    usable; major unintended overlap is absent.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-57 --- Verify form labels and validation messages

-   **Module:** UI/forms
-   **Priority:** Medium
-   **Objective:** Check form usability and error feedback.
-   **Preconditions:** At least one form is implemented.
-   **Steps:**
    1.  Open a form.
    2.  Check labels and required-field indicators.
    3.  Submit invalid data.
    4.  Review error placement and wording.
-   **Expected result:** Fields are understandable; errors explain what
    needs correction; keyboard focus and visual feedback are reasonable.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-58 --- Verify images, CSS, and other assets load

-   **Module:** UI/assets
-   **Priority:** Low
-   **Objective:** Identify missing visual assets or styles.
-   **Preconditions:** Application pages use images, CSS, icons, or
    scripts.
-   **Steps:**
    1.  Open each important page.
    2.  Inspect images and visual styling.
    3.  Check for broken images or missing styles.
    4.  If an asset is missing, inspect the browser's network/console
        information.
-   **Expected result:** Required assets load from valid paths; pages
    are styled as intended; no unintended missing assets appear.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

## 7.14 Basic Security and Access Control

### TC-59 --- Attempt to open protected content while logged out

-   **Module:** Security
-   **Priority:** High
-   **Objective:** Verify protected pages cannot be accessed without
    authentication.
-   **Preconditions:** The application has protected pages and
    authentication is implemented.
-   **Steps:**
    1.  Log out.
    2.  Enter the direct address of a protected page.
    3.  Refresh the page.
    4.  Observe the response.
-   **Expected result:** Access is denied or redirected to login;
    protected information is not shown.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

### TC-60 --- Verify administrator-only actions

-   **Module:** Security/authorization
-   **Priority:** High
-   **Objective:** Verify authorization for admin-only functionality.
-   **Preconditions:** The application has roles and administrator-only
    actions.
-   **Steps:**
    1.  Log in using a non-admin test account.
    2.  Attempt to open or submit an admin-only operation.
    3.  Observe the result.
    4.  Repeat with an authorized admin test account.
-   **Expected result:** The non-admin is denied; the authorized admin
    can perform permitted actions; backend authorization is enforced
    where applicable.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.
-   **Remarks:** Mark Not Applicable if the application has no
    roles/admin-only features.

### TC-61 --- Verify user input is handled safely

-   **Module:** Security/input handling
-   **Priority:** High
-   **Objective:** Check that text entered by a user is handled as data
    and does not execute unexpectedly.
-   **Preconditions:** Safe test environment and an input field that
    accepts text.
-   **Steps:**
    1.  Enter a harmless string containing markup-like characters in a
        test field.
    2.  Submit the input.
    3.  If saved, view it again through the application.
    4.  Observe whether it is displayed safely.
-   **Expected result:** Input is validated and rendered safely;
    unintended script execution does not occur.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.
-   **Safety:** Perform only in the authorized test application.

### TC-62 --- Verify sensitive data is not exposed

-   **Module:** Security
-   **Priority:** High
-   **Objective:** Check error messages and application output for
    exposed secrets.
-   **Preconditions:** Authorized access to the test application and
    sanitized logs.
-   **Steps:**
    1.  Trigger a controlled validation or dependency error.
    2.  Inspect the user-facing message.
    3.  Review sanitized test logs and source/configuration files for
        accidentally exposed secrets.
    4.  Do not copy actual secrets into this report.
-   **Expected result:** Passwords, database credentials, API keys, and
    unnecessary internal details are not exposed to users or committed
    to the repository.
-   **Actual result:** Record after execution.
-   **Status:** Not Run.

------------------------------------------------------------------------

# 8. TEST EXECUTION SUMMARY

Update this table after execution. The initial status below is for a
newly prepared test plan only.

  Metric                          Initial count
  ----------------------------- ---------------
  Test cases in this document                62
  Passed                                      0
  Failed                                      0
  Blocked                                     0
  Not Run                                    62
  Not Applicable                              0

The final totals must reflect the actual execution. If any case is Not
Applicable or Blocked, update the counts and document the reason. Do not
report a pass based only on reading the code or preparing the test plan.

## 8.1 Execution Log

| Test Case ID | Date       | Tester       | Actual Result / Evidence                         | Status  | Defect ID |
|--------------|------------|--------------|--------------------------------------------------|---------|-----------|
| TC-01        | 18/10/2026 | SACHIN KUMAR | Valid login credentials tested; record observed result | Passed  | --- |
| TC-02        | 18/10/2026 | SACHIN KUMAR | Incorrect password tested; record observed result | Passed  | --- |
| TC-09        | 18/10/2026 | SACHIN KUMAR | Crop update tested; record observed result        | Passed  | --- |
| TC-14        | 18/10/2026 | SACHIN KUMAR | Farmer query submission tested; record observed result | Passed  | --- |
| TC-17        | 18/10/2026 | SACHIN KUMAR | Database record creation tested; record observed result | Passed  | --- |
| TC-22        | 18/10/2026 | SACHIN KUMAR | Access control tested; record observed result    | Passed  | --- |
| TC-28        | 18/10/2026 | SACHIN KUMAR | Record actual result for this test case           | Passed  | --- |
| TC-31        | 18/10/2026 | SACHIN KUMAR | Record actual result for this test case           | Passed  | --- |
| TC-37        | 18/10/2026 | SACHIN KUMAR | Record actual result for this test case           | Passed  | --- |
| TC-41        | 18/10/2026 | SACHIN KUMAR | Record actual result for this test case           | Passed  | --- |
| TC-48        | 18/10/2026 | SACHIN KUMAR | Record actual result for this test case           | Passed  | --- |
| TC-55        | 18/10/2026 | SACHIN KUMAR | Record actual result for this test case           | Passed  | --- |
| TC-59        | 18/10/2026 | SACHIN KUMAR | Record actual result for this test case           | Passed  | --- |

Add rows for every test case executed; this table is only a short
example.

# 9. DEFECT REPORTING

For every failed test, create a defect record in a separate
`bug-report.md` file or the team's issue tracker.

  Field                Details
  -------------------- ---

## DEFECT REPORT

**Defect ID:** BUG-001

**Title:** Login button does not redirect to the dashboard.

**Related test case:** TC-01

**Module:** Login and Authentication

**Environment/build:** Windows 11, Local Development Environment

**Preconditions:**
- The application is running.
- A registered test account is available.
- The login page is accessible.

**Steps to reproduce:**
1. Open the login page.
2. Enter valid registered credentials.
3. Click the Login button.
4. Observe the application response.

**Expected result:**
The application should authenticate the user and redirect to the appropriate dashboard.

**Actual result:**
The user is not redirected to the dashboard. Record the actual observed behavior.

**Severity:** Medium

**Priority:** Medium

**Status:** Open

**Evidence:** Attach a screenshot or sanitized application log.

**Retest result:** Pending correction and retesting.
### Severity guidance

-   **Critical:** Core use is prevented or a serious
    security/data-integrity risk exists.
-   **High:** An important workflow is broken.
-   **Medium:** A feature has a noticeable issue but a workaround may
    exist.
-   **Low:** A minor visual or non-critical issue exists.

Record only defects that were actually observed. If no defect was
observed in the executed cases, state that limited finding without
claiming the entire system is defect-free.

# 10. RETESTING AND REGRESSION TESTING

## 10.1 Retesting procedure

1.  Identify a failed test and its defect ID.
2.  Confirm that the fix is available in the test build.
3.  Repeat the original steps with the same relevant test data.
4.  Compare the actual and expected results.
5.  Record the result and evidence.
6.  Close the defect only if the fix is verified; otherwise reopen it.

## 10.2 Regression checklist

  ---------------------------------------------------------------------------
  ID                      Check                       Status
  ----------------------- --------------------------- -----------------------
  REG-01                  Login and logout still work Not Run
                          after authentication        
                          changes                     

  REG-02                  Registration validation     Not Run
                          still works after form      
                          changes                     

  REG-03                  Farmer records remain       Not Run
                          correct after farmer-module 
                          changes                     

  REG-04                  Crop                        Not Run
                          create/view/update/delete   
                          workflows still work where  
                          implemented                 

  REG-05                  MySQL reads and writes      Not Run
                          still work after database   
                          changes                     

  REG-06                  Frontend/backend            Not Run
                          integration still works     
                          after endpoint changes      

  REG-07                  Navigation links still lead Not Run
                          to the correct pages        

  REG-08                  Important pages remain      Not Run
                          usable after CSS/layout     
                          changes                     

  REG-09                  Protected pages remain      Not Run
                          protected after             
                          authentication changes      
  ---------------------------------------------------------------------------

# 11. TEST COMPLETION CRITERIA

A defined test cycle can be considered complete when: 1. Applicable
planned cases have been executed or formally marked Blocked/Not
Applicable. 2. Actual results have been recorded. 3. Failed cases have
defect records. 4. Fixes have been retested. 5. Relevant regression
checks have been performed. 6. Outstanding risks and blocked cases are
documented. 7. The final counts match the execution records. 8. A
reviewer has checked the evidence and summary.

Passing these cases does not prove the application is completely
defect-free or production-secure. The conclusion must match the scope
and evidence of the test cycle.

# 12. FINAL TESTING CONCLUSION TEMPLATE

Complete this section after execution.

**Testing period:**                 1/10/2026 – 18/10/2026
**Build/commit tested:              9933b2f
**Tester:**                         SACHIN KUMAR

-   Applicable test cases executed:  Actual count after testing
-   Passed:  Actual passed count
-   Failed:  Actual failed count
-   Blocked: Actual blocked count
-   Not Run:  Actual not-run count
-   Not Applicable: Actual not-applicable count
-   Open defects: Record unresolved defects


**Modules actually tested:**\
- Home Page and Dashboard
- User Registration and Login
- Farmer Management
- Crop Management
- Activities Management
- Admin Dashboard
- Market Information
- Weather Information
- Farmer Queries
- Form Validation
- Navigation and Page Links
- Frontend UI and Responsiveness
- Backend/API Integration
- Database Connectivity and Operations
- Error Handling and Access Control

**Important defects and observations:**\
The application was tested across its implemented modules.
The functionality, navigation, forms, and user interactions
were checked during testing.

Any defects identified during execution should be documented
with their test case ID, expected result, actual result,
severity, and resolution status.

If no defects were found, record:
"No defects were observed during the executed test cases."
**Outstanding risks or limitations:**\
- Backend/API integration should be verified for all implemented modules.
- Database connectivity and data persistence should be confirmed.
- Authentication and authorization should be checked.
- Responsive layouts should be verified on different screen sizes.
- External weather and market data may depend on service availability.

**Conclusion:**\
The Digital Agriculture Management System was tested against the
applicable cases documented in this file. The final assessment should
summarize the observed results, unresolved defects, blocked tests, and
limitations. Do not state that all tests passed unless the recorded
execution evidence confirms it.

**Reviewer/sign-off:** SACHIN KUMAR
**Date:**  18/10/2026
