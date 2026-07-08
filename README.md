# Azure-Lab
Automated Azure Identity & Resource Onboarding Workflow

This lab demonstrated how to automate Azure identity creation, governance tasks

---

## Workflow Screeshot

![az104](https://github.com/user-attachments/assets/752c32f2-6ff1-4bbb-b537-c4c744267b11)

---

---

## Onboard Automator  
### Manage Azure identities and automate resource provisioning

The **Onboard Automator** is a Logic App workflow that listens for onboarding requests and automatically performs identity creation, group assignment, resource setup, and notification tasks.

This eliminates manual steps and ensures consistent, repeatable onboarding across Azure environments.

---

##  Azure Services Used

- **Azure Active Directory (Azure AD)**  
  User creation, identity management, group assignment.

- **Azure Logic Apps**  
  Workflow automation, triggers, connectors, orchestration.

- **Azure Email Service (Logic Apps Connector)**  
  Automated email notifications.

- **Azure Resource Manager (ARM)**  
  Resource group creation and VM scale set queries.

---

##  Workflow Steps

### 1. **Trigger: When a New Email Arrives (V3)**
The workflow begins when an onboarding request email is received.

### 2. **Create User**
Automatically creates a new Azure AD user with the required attributes.

### 3. **Add User to Group**
Assigns the new user to the appropriate Azure AD security group(s).

### 4. **Create or Update Resource Group**
Ensures the user’s required Azure resources exist and are properly configured.

### 5. **Get Virtual Machine in a VM Scale Set**
Queries VM scale sets to validate or prepare compute resources.

### 6. **Send Email (V2)**
Sends a confirmation or onboarding completion email.

### 7. **Run Query and List Results (V2 Preview)**
Executes additional queries for logging, validation, or reporting.

---

##  Architecture Diagram

```text
┌──────────────────────────────┐
│     Onboarding Email Input   │
└───────────────┬──────────────┘
                ▼
┌──────────────────────────────┐
│     Logic App Orchestration  │
│  - Trigger                   │
│  - Workflow Steps            │
└───────────────┬──────────────┘
                ▼
┌──────────────────────────────┐
│       Azure AD Operations    │
│  - Create User               │
│  - Add to Group              │
└───────────────┬──────────────┘
                ▼
┌──────────────────────────────┐
│     Azure Resource Manager   │
│  - Create Resource Group     │
│  - Query VM Scale Sets       │
└───────────────┬──────────────┘
                ▼
┌──────────────────────────────┐
│     Notifications & Output   │
│  - Send Email                │
│  - Run Query / Log Results   │
└──────────────────────────────┘
```

##  Setup Instructions
1. Azure AD Configuration
 - Create or use an existing Azure AD tenant.

 - Ensure permissions for user creation and group management.

2. Logic App Deployment
- Create a new Logic App in the Azure Portal.

- Add the required connectors:

- Outlook / Email

- Azure AD

- Azure Resource Manager

3. Configure Workflow Steps
- Map email fields to user attributes.

- Define group assignment logic.

- Configure ARM actions for resource creation.

- Set up email notifications.

##  Use Cases
Automated employee onboarding

- Consistent identity provisioning

- Resource setup for new team members

- Governance and access control workflows

- Cloud operations automation

##  License
- This project is licensed under the MIT License.

##  Contributing
- Pull requests and feature enhancements are welcome.
- Please open an issue for bugs or workflow improvements.

