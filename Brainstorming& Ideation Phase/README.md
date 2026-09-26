#Machal Script Control - Script-Controlled ACL
## Restrict Record Access Based on Field Value

### 1. Project Title
Script-Controlled ACL – Restrict Record Access Based on Field Value

### 2. Problem Statement
* Standard Access Control Lists (ACLs) cannot dynamically restrict record access based on complex field logic.
* Managing access control for sensitive fields manually leads to security risks and data exposure.

### 3. Proposed Solution
* Implement a Script-Controlled ACL mechanism that checks specific field values before granting Read, Write, or Delete permissions.
* Dynamically control access based on conditions (e.g., `Status == 'Restricted'`).

### 4. Key Features
* Field-Level Access Control
* Dynamic Script Evaluation
* Role-based Overrides for Admins
* Clear Error Messaging on Access Denial
