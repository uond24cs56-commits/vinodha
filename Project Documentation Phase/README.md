# Phase 7: Project Documentation Phase
## Project Documentation: Script-Controlled ACL

### Executive Summary
This project provides a server-side Script-Controlled Access Control List (ACL) mechanism designed to restrict record access based on dynamic field values.

### Installation & Setup Guide
1. **Repository Setup:** Clone or download this project repository.
2. **Environment Configuration:** Ensure server runtime (Node.js/ServiceNow Engine) is installed.
3. **ACL Deployment:**
   - Import `script_acl.js` into your server-side access control manager.
   - Bind the script trigger to record-level Read, Write, and Delete operations.

### User Guide
- **Administrators:** Admins automatically bypass field-based restrictions and hold global permission.
- **Record Owners:** Users retain access to confidential records created by themselves.
- **General Users:** Access is dynamically permitted or restricted based on the `status` field value.

### Security Best Practices
- Always execute ACL evaluation logic server-side.
- Ensure logging is enabled to track failed authorization attempts for security auditing.
-
