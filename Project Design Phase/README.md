# Phase 3: Project Design Phase
## Project: Script-Controlled ACL – Restrict Record Access Based on Field Value

### 1. System Architecture Workflow
1. **User Request:** User requests access to a specific record (Read/Write/Delete).
2. **ACL Trigger:** System triggers the Script-Controlled ACL before fetching record data.
3. **Script Evaluation:** Script fetches the target field value (e.g., `status = 'Confidential'`).
4. **Role & Condition Check:** 
   - If User has Admin Role -> **Grant Access**
   - If Field Value matches Restriction & User lacks permission -> **Deny Access**
5. **Response:** Display record data or show "Access Denied" notification.

### 2. Database Schema / Data Structure
* **Table Name:** `records`
  * `id` (Primary Key)
  * `title` (String)
  * `status` (String: 'Draft', 'Public', 'Confidential')
  * `created_by` (User ID)

### 3. Script Logic Flow
```text
IF user.role == 'Admin' THEN
    RETURN true (Allow Access)
ELSE IF record.status == 'Confidential' AND record.created_by != current_user THEN
    RETURN false (Restrict Access)
ELSE
    RETURN true (Allow Access)
END IF
