# Phase 6: Project Testing Phase
## Project: Script-Controlled ACL – Restrict Record Access Based on Field Value

### Test Cases & Execution Results

| Test Case ID | Test Scenario | Input Data / Condition | Expected Result | Actual Result | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-01** | Admin User accessing confidential record | `Role: Admin`, `Status: Confidential` | Full Access Granted | Access Granted | **PASS** |
| **TC-02** | Record Owner accessing their confidential record | `User: Owner`, `Status: Confidential` | Access Granted | Access Granted | **PASS** |
| **TC-03** | Standard User accessing another user's confidential record | `User: Non-Owner`, `Status: Confidential` | Access Denied | Access Denied | **PASS** |
| **TC-04** | Standard User accessing a public record | `User: Standard`, `Status: Public` | Access Granted | Access Granted | **PASS** |
| **TC-05** | Unauthorized user attempting Write operation | `User: Guest`, `Status: Draft` | Access Denied | Access Denied | **PASS** |

### Testing Summary
- **Total Test Cases:** 5
- **Passed:** 5
- **Failed:** 0
- **Conclusion:** The Script-Controlled ACL logic works accurately across all field-based access control scenarios.
-
