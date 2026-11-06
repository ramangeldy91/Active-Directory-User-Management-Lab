# Joiner Workflow - Employee Onboarding



## 1. Purpose and Scope



This document defines the Joiner (employee onboarding) workflow for creating user accounts and assigning access to corporate resources.



The workflow is designed to ensure that:



- New employee accounts are created based on authorized requests.

- User attributes are accurate and consistent with HR records.

- Access is assigned according to approved job responsibilities.

- The principle of Least Privilege is followed.

- All provisioning activities are validated and documented.



This workflow is designed for an enterprise identity management environment. Practical implementation in this lab uses Microsoft Entra ID with cloud-only test accounts.



## 2. Roles and Responsibilities



| Role | Responsibility |

|---|---|

| HR | Registers the new employee and provides accurate employment information. |

| Hiring Manager | Confirms the employee's position, department, and required access. |

| IT/IAM Administrator | Reviews the request, validates approvals, creates the account, and assigns access. |

| Application/Resource Owner | Approves access to resources under their responsibility when required. |



**Separation of Duties:** HR provides employment information, managers approve business access requirements, and IT/IAM administrators implement the approved access. Administrators must not independently approve business access on behalf of managers or resource owners.



## 3. Joiner Workflow



### Step 1 - HR Initiates the Onboarding Process



HR registers the new employee and provides the required information:



- Full name

- Employee ID

- Department

- Job title

- Manager

- Employment start date

- Employment status



HR information serves as the source for identity attributes used during account provisioning.



**Expected result:** Employee information is available for the onboarding request.



### Step 2 - Manager Reviews and Approves Access



The Hiring Manager reviews the employee's responsibilities and identifies the access required for the role.



The manager must confirm:



- Department and job title.

- Required security groups.

- Required applications and resources.

- Any additional access requiring separate approval.



Access requests must be based on actual job responsibilities.



**Expected result:** The access requirements are documented and approved by the appropriate authority.



### Step 3 - IAM Reviews the Request



The IT/IAM Administrator reviews the onboarding request before provisioning.



The review includes:



1. Verifying that required employee information is present.

2. Confirming that the manager's approval is documented.

3. Checking whether additional resource-owner approvals are required.

4. Reviewing requested access against the employee's job responsibilities.

5. Applying the Principle of Least Privilege.



If the request is incomplete or approvals are missing, provisioning must be paused until the issue is resolved.



**Expected result:** The request is validated and ready for provisioning.



### Step 4 - Create the User Account



The IT/IAM Administrator creates the employee's user account in the identity management system.



The account must contain accurate identity attributes, including:



- Display Name

- User Principal Name (UPN)

- Employee ID

- Department

- Job Title

- User Type



Additional account settings must follow organizational security policies.



Administrative privileges and licenses must not be assigned unless explicitly required and approved.



**Expected result:** The user account is created with the correct identity attributes.



### Step 5 - Assign Security Groups



The IT/IAM Administrator assigns the employee to the appropriate security groups based on the approved access requirements.



For example:



| Employee Department | Example Security Group |

|---|---|

| IT Support | GRP-IT-Support-Basic |

| HR | GRP-HR-Basic |

| Finance | GRP-Finance-Basic |



Before assigning a group, the administrator must verify that it matches the employee's approved role requirements.



Access must not be granted simply because a group exists or because another employee has similar access.



**Expected result:** The employee is added only to the approved security groups.



### Step 6 - Verify the Provisioning Result



The IT/IAM Administrator verifies that provisioning was completed successfully.



Validation includes:



- Confirming that the user account exists.

- Checking the employee's identity attributes.

- Verifying the account status.

- Checking security group membership.

- Confirming that no unauthorized administrative roles or excessive access were assigned.

- Verifying application or resource access where the environment supports it.



If validation fails, the issue must be investigated and corrected before the onboarding request is closed.



**Expected result:** The account and assigned access match the approved onboarding request.



### Step 7 - Document Activities and Close the Request



The IT/IAM Administrator records the provisioning results in the relevant ticketing or identity management system.



Documentation should include:



- Employee ID and account identifier.

- Request and approval references.

- Account creation date.

- Assigned security groups.

- Validation results.

- Any errors, exceptions, or corrective actions.

- Completion status.



The onboarding request can be closed after all required provisioning and validation activities have been completed.



**Expected result:** The onboarding process has an auditable record and a documented completion status.



## 4. Exception Handling



| Scenario | Required Action |

|---|---|

| Missing employee information | Pause provisioning and request the missing information from HR. |

| Missing manager approval | Do not assign access; return the request for approval. |

| Missing resource-owner approval | Hold the relevant access assignment until approval is received. |

| Unclear access requirements | Request clarification from the manager or resource owner. |

| User account creation failure | Investigate the error, document the result, and retry after correcting the issue. |

| Security group assignment failure | Verify the group and account, investigate the error, and retry if appropriate. |

| Unexpected or excessive access | Do not proceed with the unauthorized assignment; investigate and correct the access configuration. |

| Validation failure | Keep the request open until the issue is resolved or formally escalated. |



All exceptions must be documented to maintain accountability and traceability.



## 5. Security and Access Control Requirements



The following security principles apply throughout the Joiner workflow:



- **Least Privilege:** Assign only the access required for the employee's job responsibilities.

- **Separation of Duties:** Business approval and technical provisioning must remain separate responsibilities.

- **Approval-Based Access:** Access must be supported by documented authorization.

- **Accountability:** Provisioning actions must be traceable to an administrator and a request.

- **Validation:** Account attributes and group memberships must be checked after provisioning.

- **Data Accuracy:** Identity attributes must match the authoritative employment information.

- **Auditability:** Relevant administrative activities must be recorded and retained according to organizational policy.



## 6. Validation and Evidence



The practical implementation of this workflow was tested using a cloud-only Microsoft Entra ID environment.



The lab validation covered:



- Creation of a test user account.

- Verification of employee identity attributes.

- Assignment to the IT Support security group.

- Verification of group membership.

- Review of Microsoft Entra audit log events.



The following evidence is maintained in the repository:



`evidence/Joiner-Onboarding/`



The evidence includes user properties, group membership, audit logs, and a test report.



## 7. Environment Limitations



This lab demonstrates selected technical provisioning and validation activities using Microsoft Entra ID cloud-only accounts.



The following activities are documented as part of the enterprise workflow but were not executed through a real corporate system:



- HR onboarding request submission.

- Actual manager approval.

- Application or resource-owner approval.

- Integration with an HR information system.

- Automated provisioning through an enterprise workflow platform.

- Verification of access to individual business applications.



Security group membership was verified, but this does not independently prove access to a specific application or resource.



No real employee information was used.



## 8. Conclusion



The Joiner workflow establishes a controlled and auditable process for onboarding new employees.



By separating HR responsibilities, business approvals, and IT/IAM provisioning, the process reduces the risk of unauthorized access and incorrect account configuration.



The workflow supports consistent identity lifecycle management and the implementation of the Principle of Least Privilege.



