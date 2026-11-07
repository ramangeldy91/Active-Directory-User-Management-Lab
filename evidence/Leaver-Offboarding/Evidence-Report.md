# Leaver Offboarding - Evidence Report



## 1\. Overview



**Scenario:** Employee Offboarding (Leaver)

**Test User:** Leaver Test User 01

**Employee ID:** LAB-USER-003

**Department:** IT Support

**Environment:** Microsoft Entra ID (Cloud-only)



## 2\. Objective



The objective was to perform and validate the key identity offboarding actions:



* Disable the user account.
* Revoke active sign-in sessions.
* Remove the user from the assigned security group.
* Verify the resulting account and group membership state.
* Review administrative activity in Entra Audit Logs.



## 3\. Actions Performed



| Action | Result |

|---|---|

| Created dedicated test user | Completed |

| Added user to GRP-IT-Support-Basic | Completed |

| Disabled user account | Successful |

| Revoked sign-in sessions | Successful |

| Removed user from GRP-IT-Support-Basic | Successful |

| Verified account disabled state | Confirmed |

| Verified group membership removal | Confirmed |

| Reviewed Entra Audit Logs | Completed |



## 4\. Evidence Files



| File | Description |

|---|---|

| 01-Leaver-Before-Offboarding.png | User account and initial group membership |

| 02-Leaver-Account-Disabled.png | Disabled account state |

| 03-Leaver-Group-Access-Removed.png | Group membership removal |

| 04-Leaver-Audit-Logs.png | Administrative audit events |



## 5\. Audit Log Verification



The following administrative events were identified:



* **Update user** - account update associated with disabling the user.
* **Remove member from group** - removal of the user's group membership.



The session revocation action was successfully performed in the portal. A separate corresponding audit event was not independently confirmed in the reviewed results.



## 6\. Final Validation



* The test account is disabled.
* The user is no longer a member of GRP-IT-Support-Basic.
* Sign-in sessions were successfully revoked through the Entra admin center. A separate audit event for this action was not independently confirmed.
* Relevant administrative activity was recorded in Audit Logs.



**Result:** The practical Leaver offboarding scenario was completed successfully.



## 7\. Environment Limitations



This lab uses a cloud-only Microsoft Entra ID test account.



The following enterprise processes were documented but not implemented in the lab:



* Actual HR termination request and approval.
* Manager and resource-owner approval.
* Automated HRIS integration.
* Application-specific session and token revocation.
* Corporate device management and data retention.
* Permanent account deletion.



Group membership removal does not independently prove that all application and resource permissions have been revoked.



Account deletion remains a separate process governed by organizational retention and deletion policies. The test account was intentionally retained in a disabled state.



No real employee accounts or production resources were used.

