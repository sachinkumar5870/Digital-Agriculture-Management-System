# DIGITAL AGRICULTURE MANAGEMENT SYSTEM
# SOFTWARE TESTING REPORT

**Document ID:** DAMS-STR-001  
**Document Version:** 1.0  
**Prepared By:** SACHIN KUMAR  
**Project:** Digital Agriculture Management System  
**Report Date:** 18 October 2026  
**Testing Environment:** Local / Development  
**Report Status:** Test report template for recording actual execution results

---

## Document Control

| Field | Details |
|---|---|
| Project Name | Digital Agriculture Management System |
| Document Name | Software Testing Report |
| Document ID | DAMS-STR-001 |
| Version | 1.0 |
| Prepared By | SACHIN KUMAR |
| Reviewed By | Pending reviewer review |
| Approval Status | Pending review |
| Report Date | 18/10/2026 |
| Related Test Document | `test-cases.md` |
| Related Defect Log | Defects identified during execution, if any |

## 1. Executive Summary

This report defines the testing scope, environment, approach, execution records, defect handling, and release assessment for the Digital Agriculture Management System (DAMS). The project test-case document contains test case identifiers up to **TC-59**. The presence of these identifiers does not by itself establish that all 59 cases have been executed or passed.

The report is intended to document the actual outcome of testing. Counts for Passed, Failed, Blocked, Not Run, and Not Applicable must be calculated from the completed execution log in `test-cases.md`. No test result should be marked Passed without evidence that the observed result matched the expected result.

### 1.1 Current Report Status

| Measure | Current value |
|---|---|
| Documented test-case range | TC-01 through TC-59 |
| Total documented test cases | 59, subject to confirming that every ID is present and unique |
| Passed | To be calculated from execution log |
| Failed | To be calculated from execution log |
| Blocked | To be calculated from execution log |
| Not Run | To be calculated from execution log |
| Not Applicable | To be calculated from execution log |
| Open defects | To be counted from the defect log |
| Overall assessment | Pending verified execution results |

### 1.2 Summary

The report provides a structured record for functional testing, user-interface testing, form validation, navigation, backend/API integration, database operations, access control, compatibility, and error handling where these features are implemented. Modules and tests that do not exist in the current build should be marked Not Applicable, not assumed to have passed.

## 2. Project Overview

The Digital Agriculture Management System is a software project intended to support agricultural information and management workflows. The repository includes frontend HTML pages and CSS files, and a `backend` directory. The exact behavior and availability of each feature must be confirmed against the current project build.

### 2.1 Objectives of Testing

The testing objectives are to:

1. Verify that implemented pages open and render correctly.
2. Check navigation links and page-to-page workflows.
3. Validate input handling on registration, login, crop, farmer, and query forms where present.
4. Verify that successful and unsuccessful form submissions produce appropriate responses.
5. Check backend endpoints and database operations if configured and available.
6. Check authentication and role-based access control if implemented.
7. Identify, document, prioritize, and retest defects.
8. Record actual evidence so that the final assessment is reproducible.
9. Provide a transparent summary of test coverage and remaining risks.

### 2.2 Intended Audience

This report is intended for the project team, tester, faculty guide/reviewer, and anyone reviewing the project’s testing evidence.

## 3. Scope of Testing

The final scope must match the features implemented in the tested build.

### 3.1 In-Scope Areas

| Area | Checks to record |
|---|---|
| Home page/dashboard | Page loads, visible content, key links and controls |
| Registration | Required fields, valid input, invalid input, duplicate account handling if supported |
| Login | Valid credentials, invalid credentials, empty fields, appropriate destination |
| Farmer management | Add, view, edit, delete/search operations only where implemented |
| Crop management | Add, view, edit, delete/search operations only where implemented |
| Activities | Activity page loads and implemented actions behave correctly |
| Market information | Data or an appropriate empty/error state is shown |
| Weather information | Data or an appropriate empty/error state is shown |
| Farmer queries | Form validation and submission behavior |
| Admin pages | Admin workflows and access restrictions if implemented |
| Navigation | Menu links, internal links, back/forward behavior, broken paths |
| UI and responsiveness | Layout, readability, overflow, controls at tested viewport sizes |
| Backend/API | Valid/invalid requests, response codes and payloads, if API exists |
| Database | Create/read/update/delete and persistence, if database integration exists |
| Error handling | Clear response to invalid input, unavailable service, or failed operation |
| Security/access | Authentication, authorization, input handling, and exposure of sensitive data where applicable |

### 3.2 Out of Scope Unless Specifically Implemented

- Third-party services not configured in the test environment.
- Production load and stress testing unless a performance test was run.
- Formal penetration testing unless explicitly performed.
- Real farmer/customer personal data; use synthetic test data where possible.
- Features not present in the tested version.

### 3.3 Scope Limitations

A page opening successfully does not prove that its backend, database, or business logic works. UI-only checks must be reported as UI checks and should not be described as full integration or database verification.

## 4. Test Environment

Fill or verify each item against the machine and build actually used.

| Field | Recorded value |
|---|---|
| Operating system | Windows 11 (reported test environment; verify if the test used another machine) |
| Browser | Record browser name and exact version |
| Frontend | HTML, CSS, JavaScript (confirm the tested build) |
| Backend | Java / Spring Boot is present in project context; record the actual framework and version used for this test run |
| Database | MySQL is indicated in project context; verify the actual database and version |
| Database tool | MySQL Workbench or the configured database tool; record the one actually used |
| Application URL | `http://127.0.0.1:5500/index.html` if this was the URL used |
| Database/schema | `digital_agriculture_db` if this was the schema used |
| Environment | Local / Development |
| Git repository | `sachinkumar5870/AGRICULTURE-MANAGEMENT-SYSTEM` (confirm the repository/build under test) |
| Git branch | Record the actual branch, e.g. `main` only if that was the tested branch |
| Tested commit ID | Record the commit hash that was tested; do not substitute a newer commit |
| Test date | 18/10/2026 if this is the actual execution date |
| Tester | SACHIN KUMAR |

### 4.1 Build Identification

The build/commit ID must identify the exact version tested. To obtain it from the correct Git repository, open a terminal in the repository root and run:

```powershell
git rev-parse --short HEAD
git branch --show-current
```

If Git reports that the current directory is not a repository, first open the actual repository folder containing the `.git` directory. Do not use a commit hash copied from a different repository or from an unverified screenshot.

### 4.2 Test Data and Safety

- Use synthetic accounts and sample farmer/crop records.
- Do not include passwords, tokens, private API keys, or personal customer data in this report.
- Remove or mask confidential data in screenshots and logs.
- Record the sample data used when it is needed to reproduce a defect.
- Clean up test records only when doing so is safe and permitted.

## 5. Test Strategy and Methodology

### 5.1 Test Levels

**Component/UI testing:** Check individual pages, components, forms, styles, and controls.

**Functional testing:** Compare the observed feature behavior with the documented expected result.

**Integration testing:** Verify data exchange between the frontend, backend, and database when all are configured.

**System testing:** Test end-to-end workflows through the application.

**Regression testing:** Repeat relevant tests after a defect fix or code change.

**Compatibility testing:** Check supported browsers and viewport sizes that are actually available.

**Security-oriented checks:** Verify basic access restrictions and input handling where applicable. These checks do not constitute a formal security audit.

### 5.2 Test Design Techniques

- Positive testing: valid input and normal workflow.
- Negative testing: invalid input, missing fields, invalid credentials, or unavailable dependencies.
- Boundary testing: minimum/maximum field lengths and numeric ranges where requirements define them.
- State-transition testing: login/logout, record creation/update, and status changes where supported.
- Exploratory testing: investigate unexpected behavior and record reproducible findings.

### 5.3 Entry Criteria

Testing can begin when:

- The intended build is available.
- The required local services are running.
- Test accounts and safe test data are available.
- The tester can access the pages and functions in scope.
- Expected behavior is understood sufficiently to judge results.

### 5.4 Exit Criteria

Testing may be considered complete for the defined scope when:

- All applicable test cases have an execution status.
- Actual results and evidence are recorded for executed cases.
- Failed tests have linked defect records.
- Blocked and Not Applicable cases have reasons.
- Relevant fixes have been retested.
- Remaining defects and risks are documented.
- The reviewer has enough evidence to make an informed decision.

## 6. Test Case Status Definitions

| Status | Definition |
|---|---|
| Passed | The observed result matches the expected result, with evidence recorded. |
| Failed | The observed result differs from the expected result; a defect should be logged. |
| Blocked | Execution cannot continue because a dependency, environment, account, or prerequisite is unavailable. Record the reason. |
| Not Run | The test has not been executed. |
| Not Applicable | The test does not apply to the implemented scope; record the reason. |
| Retest | A previously failed test is being executed again after a change. Record the final outcome separately. |

## 7. Test Execution Procedure

For each case in `test-cases.md`:

1. Read the test case ID, module, preconditions, test data, steps, and expected result.
2. Confirm that the relevant application build and services are available.
3. Execute the steps in the documented order.
4. Record what actually happened, not what was expected to happen.
5. Compare actual and expected results.
6. Set the status using the definitions in Section 6.
7. Capture a screenshot, sanitized log, API response, or database query result where appropriate.
8. For a failure, create a defect entry and link its ID to the test case.
9. For a blocked test, record the blocking reason and required action.
10. After a fix, record the retest result and the build used for retesting.

## 8. Test Execution Summary

### 8.1 Execution Log

The detailed execution log is maintained in `test-cases.md`. It should contain a row for every documented test case, not only selected examples.

| Test Case ID range | Requirement |
|---|---|
| TC-01 to TC-59 | Record the actual date, tester, observed result/evidence, status, and defect ID where applicable. |

Do not treat the sample rows in the test-case document as evidence that a test passed. Check each test’s own steps and expected result.

### 8.2 Execution Count Summary

Complete the counts after reviewing every row in the execution log.

| Metric | Count |
|---|---:|
| Total documented test cases | 59 |
| Passed | Pending count from actual execution log |
| Failed | Pending count from actual execution log |
| Blocked | Pending count from actual execution log |
| Not Run | Pending count from actual execution log |
| Not Applicable | Pending count from actual execution log |
| Total status assignments | Must reconcile to the 59 documented cases |

**Reconciliation rule:** Passed + Failed + Blocked + Not Run + Not Applicable should equal the total number of documented test cases (59), provided the test cases have unique IDs and each has exactly one final status.

### 8.3 Test Coverage

| Coverage measure | Result |
|---|---|
| Documented test cases | 59 |
| Test cases with a recorded final status | Calculate from execution log |
| Test cases with evidence attached/referenced | Calculate from execution log |
| Failed cases with defect IDs | Calculate from execution log |
| Blocked cases with reasons | Calculate from execution log |
| Cases awaiting retest | Calculate from execution log |

## 9. Defect Management

### 9.1 Defect Lifecycle

A defect can move through these states according to the team’s process:

**Open → In Progress → Fixed → Retest → Closed**

If retesting fails, return the defect to Open or In Progress and record the new evidence. Do not mark a defect Closed solely because code was changed; verify the fix.

### 9.2 Severity Definitions

| Severity | Meaning |
|---|---|
| Critical | The application or a critical workflow is unusable, major data loss occurs, or there is a severe security impact. |
| High | A major feature is unusable and no reasonable workaround exists. |
| Medium | A feature has a meaningful defect, but other core functions remain usable or a workaround exists. |
| Low | Minor visual, wording, alignment, or low-impact usability issue. |

### 9.3 Priority Definitions

| Priority | Meaning |
|---|---|
| High | Fix urgently before the affected workflow is relied upon or released. |
| Medium | Fix in the planned development cycle. |
| Low | Fix when practical; limited impact. |

### 9.4 Defect Record Template

Create one record per confirmed defect.

```markdown
### Defect ID: BUG-001

- **Title:** Short, factual summary of the observed defect
- **Related test case:** TC-__
- **Module:** Actual affected module
- **Environment/build:** OS, browser, branch, and tested commit
- **Preconditions:** Required state before reproducing the defect
- **Steps to reproduce:**
  1. Step one
  2. Step two
  3. Step three
- **Expected result:** Behavior specified by the requirement/test case
- **Actual result:** Behavior observed during execution
- **Severity:** Critical / High / Medium / Low
- **Priority:** High / Medium / Low
- **Status:** Open / In Progress / Fixed / Retest / Closed
- **Evidence:** Screenshot or sanitized log reference
- **Assigned to:** Responsible team member, if assigned
- **Reported by:** SACHIN KUMAR
- **Date reported:** Actual date
- **Fix/build reference:** Commit or change reference, if available
- **Retest result:** Pending / Passed / Failed / Not applicable
- **Closure date:** Actual date when closed, if applicable
```

If no defects were found, state that no defects were identified **in the executed test scope**. Do not create a fictional defect or claim that untested areas are defect-free.

### 9.5 Defect Summary

| Measure | Count |
|---|---:|
| Total defects identified | Fill from defect log |
| Critical | Fill from defect log |
| High | Fill from defect log |
| Medium | Fill from defect log |
| Low | Fill from defect log |
| Open | Fill from defect log |
| In Progress | Fill from defect log |
| Fixed, awaiting retest | Fill from defect log |
| Closed after successful retest | Fill from defect log |

## 10. Evidence Management

Evidence should be stored in a project folder such as `testing/evidence/` if the team uses that structure.

Recommended evidence names:

- `TC-01-login-valid.png`
- `TC-02-login-invalid.png`
- `TC-09-crop-update.png`
- `TC-14-farmer-query.png`
- `TC-17-database-record.png`
- `BUG-001-reproduction.png`

Use names that match the actual test case and defect. These are naming examples, not proof that the screenshots exist.

For each evidence item, record:

| Field | Description |
|---|---|
| Evidence ID | Unique evidence reference |
| Related test case/defect | TC ID or BUG ID |
| File name/path | Actual stored file path |
| Capture date | Actual date captured |
| Description | What the evidence demonstrates |
| Data protection | Confirm secrets and personal data are masked |

Do not commit passwords, access tokens, production credentials, or private API keys to the public repository.

## 11. Test Results by Area

Complete each row based on the corresponding executed test cases.

| Area | Result | Evidence/reference | Notes |
|---|---|---|---|
| Home page/dashboard | Pending verification | Link applicable TC IDs | Record load/render result |
| Registration | Pending verification | Link applicable TC IDs | Record valid/invalid-input result |
| Login | Pending verification | Link applicable TC IDs | Record success and failure behavior |
| Farmer management | Pending verification | Link applicable TC IDs | Record only implemented CRUD operations |
| Crop management | Pending verification | Link applicable TC IDs | Record only implemented CRUD operations |
| Activities | Pending verification | Link applicable TC IDs | Record implemented behavior |
| Market information | Pending verification | Link applicable TC IDs | Record source/data/empty state |
| Weather information | Pending verification | Link applicable TC IDs | Record source/data/error state |
| Farmer queries | Pending verification | Link applicable TC IDs | Record validation and submission |
| Admin functionality | Pending verification | Link applicable TC IDs | Include access checks if implemented |
| Navigation | Pending verification | Link applicable TC IDs | Record broken links, if any |
| UI/responsiveness | Pending verification | Link applicable TC IDs | State tested browsers and widths |
| Backend/API | Pending verification | Link applicable TC IDs | Only if backend endpoints were tested |
| Database | Pending verification | Link applicable TC IDs | Only if data operations were verified |
| Security/access control | Pending verification | Link applicable TC IDs | Basic checks are not a formal audit |

## 12. Risk and Limitation Assessment

The following are areas to assess, not confirmed defects.

| Risk / limitation | Potential impact | Verification or mitigation |
|---|---|---|
| Backend not started or unavailable | UI may appear usable while data operations fail | Verify service health and endpoint responses |
| Database configuration mismatch | Records may not save or retrieve correctly | Verify connection settings and safe CRUD operations |
| External weather/market source unavailable | Information may be stale or absent | Check error handling and source availability |
| Insufficient input validation | Invalid or unexpected values may be accepted | Execute positive, negative, and boundary tests |
| Access restrictions not enforced | Unauthorized users may reach restricted actions | Test access rules for each implemented role |
| Browser/viewport differences | Layout or behavior may vary | Test supported browsers and screen sizes |
| Missing execution evidence | Results cannot be independently verified | Link evidence to the relevant test case |
| Unresolved defects | Users may encounter known failures | Prioritize, fix, and retest before approval |

Mark each risk as Open, Mitigated, Accepted, or Not Applicable only after assessment.

## 13. Recommendations

1. Keep `test-cases.md` as the detailed source of test steps and execution statuses.
2. Keep this `testing-report.md` as the summary of scope, environment, results, defects, risks, and conclusion.
3. Record a final status for every applicable test case.
4. Link each failed case to a defect record.
5. Retest fixes on a clearly identified build.
6. Verify backend and database behavior separately from frontend appearance.
7. Store screenshots and sanitized logs with stable references.
8. Recalculate the execution and defect summaries after each test run.
9. Obtain reviewer approval before declaring the report formally approved.

## 14. Final Testing Assessment

**Project:** Digital Agriculture Management System  
**Tester:** SACHIN KUMAR  
**Test date:** 18/10/2026, if this is the actual test date  
**Tested build/commit:** Record the verified commit hash  
**Total documented test cases:** 59

### Final result counts

- **Passed:** To be calculated from the completed execution log.
- **Failed:** To be calculated from the completed execution log.
- **Blocked:** To be calculated from the completed execution log.
- **Not Run:** To be calculated from the completed execution log.
- **Not Applicable:** To be calculated from the completed execution log.
- **Open defects:** To be calculated from the defect log.

### Conclusion

The Digital Agriculture Management System has a documented test-case set with identifiers extending through TC-59. This report defines how the test environment, execution outcomes, evidence, defects, and risks are to be recorded.

The final quality assessment must be based on the actual test execution log and defect records. A release recommendation should be made only after the counts reconcile, failed cases are reviewed, blocked cases have documented reasons, and outstanding defects and limitations are assessed.

**Overall status:** Pending reconciliation of the actual execution log.

**Prepared by:** SACHIN KUMAR  
**Reviewer:** Pending review  
**Reviewer decision:** Pending review  
**Approval date:** Pending review

---

## Appendix A: Pre-Submission Checklist

- [ ] Confirm the exact tested Git repository, branch, and commit.
- [ ] Confirm OS, browser/version, frontend, backend, and database versions.
- [ ] Confirm all 59 documented test cases have unique IDs.
- [ ] Record the actual status for every test case.
- [ ] Ensure execution counts sum to 59.
- [ ] Attach or reference evidence for executed cases.
- [ ] Link failed tests to defect IDs.
- [ ] Document reasons for Blocked and Not Applicable cases.
- [ ] Retest fixes and record retest outcomes.
- [ ] Remove secrets and private information from evidence.
- [ ] Update this report’s summary tables from the execution log.
- [ ] Obtain reviewer sign-off where required.

## Appendix B: Revision History

| Version | Date | Author | Description |
|---|---|---|---|
| 1.0 | 18/10/2026 | SACHIN KUMAR | Initial detailed testing-report document |
