# Joiner Onboarding - Evidence Report



## 1. Overview



**Scenario:** New Employee Onboarding (Joiner)

**Test User:** Emily Carter

**Employee ID:** LAB-USER-002

**Department:** IT Support

**Job Title:** IT Support Specialist

**Identity Platform:** Microsoft Entra ID (Cloud-only)



## 2. Provisioning Evidence



The test user account was successfully created in Microsoft Entra ID.



The account status was verified as Enabled.



The account was created without administrative roles or license assignments.



The following user attributes were configured:

- First Name: Emily

- Last Name: Carter

- Department: IT Support

- Job Title: IT Support Specialist

- Employee ID: LAB-USER-002

- User Type: Member

- Usage Location: Georgia



## 3. Group Assignment Evidence



The user was successfully added to:



`GRP-IT-Support-Basic`



No additional groups or administrative roles were assigned.



## 4. Validation Results



The following checks were completed successfully:



| Validation Check | Result |

|---|---|

| User account creation | PASS |

| Account status verification (Enabled) | PASS |

| Employee ID verification | PASS |

| Department verification | PASS |

| Job Title verification | PASS |

| Group membership verification | PASS |

| Audit log verification | PASS |



**Total: 7 checks passed.**



## 5. Audit Log Evidence



Microsoft Entra Audit Logs recorded the following administrative activities:



| Service | Activity |

|---|---|

| Core Directory | Add user |

| Core Directory | Add member to group |



These events provide an audit trail for account creation and group membership assignment.



## 6. Security Considerations



- Access was assigned according to the defined IT Support role requirements in this lab scenario.

- Least Privilege was applied by assigning only the required IT Support group.

- No administrative roles or licenses were assigned.

- No real employee information was used.



## 7. Environment Limitations



This lab uses a cloud-only Microsoft Entra ID test environment.



The HR initiation and manager approval stages are documented workflow steps and were not executed through a real corporate HR or approval system.



Group membership was verified, but access to individual applications and resources was not tested.



## 8. Conclusion



The Joiner provisioning scenario was successfully completed in Microsoft Entra ID.



The test account was created, the required security group was assigned, user attributes were verified, and the corresponding administrative activities were confirmed in Audit Logs.


