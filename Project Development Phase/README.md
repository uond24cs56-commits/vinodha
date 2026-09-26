/**
 * Script-Controlled ACL - Restrict Record Access Based on Field Value
 * Description: Evaluates record access dynamically based on field values and user roles.
 */

function checkRecordAccess(currentRecord, currentUser) {
    // 1. Admin Override - System Admins always get full access
    if (currentUser.roles.includes('admin')) {
        return {
            allowAccess: true,
            message: "Access granted: Admin privilege."
        };
    }

    // 2. Extract field value to evaluate
    var recordStatus = currentRecord.status; // e.g., 'Draft', 'Confidential', 'Public'
    var recordOwner = currentRecord.created_by;

    // 3. Condition Check: Restrict access if record status is 'Confidential'
    if (recordStatus === 'Confidential') {
        // Only the creator of the record can access it
        if (currentUser.id === recordOwner) {
            return {
                allowAccess: true,
                message: "Access granted: Record owner."
            };
        } else {
            return {
                allowAccess: false,
                message: "Access Denied: Record is marked as Confidential."
            };
        }
    }

    // 4. Default Rule: Allow access for 'Public' or 'Draft' records
    return {
        allowAccess: true,
        message: "Access granted: Public record."
    };
}

// Example Execution Usage
var sampleRecord = { id: 101, title: "Quarterly Audit Report", status: "Confidential", created_by: "user_001" };
var sampleUser = { id: "user_002", roles: ["standard_user"] };

var accessResult = checkRecordAccess(sampleRecord, sampleUser);
console.log(accessResult.message);
