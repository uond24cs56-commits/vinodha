# Phase 2: Requirement Analysis Phase
## Project: Script-Controlled ACL – Restrict Record Access Based on Field Value

### 1. Functional Requirements
* **FR-1:** System must evaluate record field values dynamically before granting access.
* **FR-2:** Restrict Read, Write, and Delete operations if field value conditions are not met.
* **FR-3:** Provide administrative overrides for System Administrators.
* **FR-4:** Log all unauthorized access attempts for security audit trails.

### 2. Non-Functional Requirements
* **Performance:** ACL script evaluation time must be under 100ms per record request.
* **Security:** Access control rules must be evaluated server-side to prevent client-side bypass.
* **Scalability:** System should handle high concurrent record requests without degrading performance.

### 3. User Roles & Permissions
* **Admin:** Full access to all records and ACL configuration settings.
* **Manager:** Read and Write access to records assigned to their team.
* **Standard User:** Restricted access based strictly on record field values (e.g., `Status == 'Public'`).

### 4. Software & Hardware Requirements
* **OS:** Windows / Linux / macOS
* **Platform/Tools:** ServiceNow / Node.js Environment / Database System
* **Browser:** Any modern Web Browser (Chrome, Edge, Firefox)
*
