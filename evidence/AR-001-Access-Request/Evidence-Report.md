# AR-001 - Access Request & Approval Evidence Report

## 1. Overview

**Scenario:** IT Support Basic Access Request  
**Request ID:** AR-001  
**Test User:** Password Reset Test User 01  
**Employee ID:** LAB-USER-004  
**Target Group:** GRP-IT-Support-Basic  
**Environment:** Microsoft Entra ID Free, cloud-only lab  
**Execution Date:** 2026-11-07  

## 2. Objective

Demonstrate an access request workflow covering business justification, documented approval, least-privilege review, group membership provisioning, and audit verification.

## 3. Initial State

The test user was confirmed not to be a member of any groups before provisioning.

Evidence:
- `01-Before-Access-Provisioning.png`

## 4. Approval and Authorization

A lab access request was documented with an IT Support business justification and a simulated IT Support Manager approval.

The approval was recorded in the request documentation. It was not processed through a real Entra ID approval workflow, and no real manager approval was obtained.

## 5. Provisioning

The user was manually added to the Entra security group through Microsoft Entra Admin Center:

`GRP-IT-Support-Basic`

The user subsequently appeared in the group's membership list.

## 6. Audit Verification

The Entra Audit Log recorded:

- **Service:** Core Directory
- **Category:** GroupManagement
- **Activity:** Add member to group
- **Status:** Success

The target user was identified by the audit event's user identifier.

The target group's Object ID matched the Object ID displayed in the Entra group properties.

The initiating actor was identified as a user-type identity with a UPN. Its display name field was empty.

Evidence:
- `02-Access-Provisioning-Audit-Log.png`

## 7. Final Validation

| Validation | Result |
|---|---|
| Initial group membership checked | Passed |
| Access request documented | Passed |
| Approval limitation documented | Passed |
| Least-privilege rationale documented | Passed |
| Group membership provisioning | Passed |
| Audit event status verified | Passed |
| Target group Object ID matched | Passed |
| Final group membership confirmed | Passed |

## 8. Conclusion

The lab demonstrated the technical execution and verification of an access request workflow in Microsoft Entra ID.

The directory-level group membership change was successful and supported by audit evidence.

The approval stage was documented as a lab simulation. Actual manager approval, automated approval processing, and application-level access validation were not performed.

Group membership alone does not prove effective access to a specific application or resource.
