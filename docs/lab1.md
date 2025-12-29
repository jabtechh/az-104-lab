
---
title: Lab 1: Azure AD Fundamentals & Tenant Setup
parent: Domain 1: Manage Azure Identities and Governance
nav_order: 1
---

# LAB 1: Azure Active Directory (Entra ID) Fundamentals & Tenant Setup

## Concepts First
### What is Azure Active Directory (now Microsoft Entra ID)?
Azure AD is Microsoft's cloud-based identity and access management service. Think of it as the "bouncer" for your Azure resources—it determines who can access what.

**Key Concepts:**
- **Tenant:** Your organization's dedicated Azure AD instance (e.g., contoso.onmicrosoft.com)
- **Directory:** The container for all your identity objects (users, groups, apps)
- **Domain:** Custom domain names you can add to your tenant
- **License Types:** Free, P1, P2—each unlocks different features

**Why This Matters for AZ-104:**
Understanding Azure AD is fundamental—it's the foundation for ALL Azure access control. The exam heavily tests your knowledge of user/group management, authentication methods, and access control.

---

## Part 1A: Exploring Your Azure AD Tenant
### Step-by-Step: Azure Portal Navigation
1. **Access Azure Portal**
   - Navigate to: https://portal.azure.com
   - Sign in with your Azure administrator account
   - ⚠️ Ensure you have at least "User Administrator" or "Global Administrator" role
2. **Navigate to Azure Active Directory**
   - In the left menu, click "Azure Active Directory"
   - Or use the search bar at the top
   - You'll see the Azure AD Overview page
3. **Understand the Overview Dashboard**
   - Tenant Information: Name, Tenant ID, Primary domain, License
4. **Explore Tenant Properties**
   - Click "Properties" under "Manage"
   - Review: Name, Country/Region (cannot change), Notification language, Technical contact
5. **Check License Status**
   - Click "Licenses" > "All products"
   - Verify available licenses

| License Type | Features Included |
|--------------|------------------|
| Azure AD Free | Basic user/group management, SSO, B2B |
| Azure AD P1   | Self-service features, dynamic groups, Conditional Access |
| Azure AD P2   | Identity Protection, PIM, Access Reviews |

---

## Part 1B: Custom Domain Configuration
### Why Add Custom Domains?
By default, your tenant uses [name].onmicrosoft.com. Adding custom domains (like contoso.com) makes user accounts look professional.

### Step-by-Step: Adding a Custom Domain
1. In Azure AD, click "Custom domain names" under "Manage"
2. Click "+ Add custom domain"
3. Enter your domain name (e.g., contoso.com)
4. Click "Add domain"
5. **Verify Domain Ownership**
   - Azure provides a TXT DNS record to add at your registrar
   - Add the record, wait for DNS propagation
6. Return to Azure Portal, select your domain, click "Verify"
7. (Optional) Set as Primary Domain
   - Select your verified domain, click "Make primary"

> **Exam Tip:** Know the difference between "verified" and "primary" domains. You can have multiple verified domains but only ONE primary domain.

---

## Part 1C: Directory Roles Overview
### Understanding Built-in Directory Roles
- In Azure AD, click "Roles and administrators" under "Manage"
- 100+ built-in roles available

**Key Roles to Know:**
| Role                 | Permissions                        | Use Case                  |
|----------------------|------------------------------------|---------------------------|
| Global Administrator | Full access to everything           | Break-glass account only  |
| User Administrator   | Manage users, groups, passwords     | Day-to-day user management|
| Security Administrator | Manage security features, policies | Security team member      |
| Billing Administrator | Manage billing, subscriptions      | Finance team member       |
| Helpdesk Administrator | Reset passwords for non-admins     | Support desk staff        |

- Click any role to view assignments and add new ones

> **Best Practice:** Assign the MINIMUM role needed for each task (principle of least privilege).

---

## Part 1D: Understanding Azure AD Join Types
### Device Identity
Devices can have different relationships with Azure AD:

| Join Type              | Description                                 | Use Case                        |
|------------------------|---------------------------------------------|---------------------------------|
| Azure AD Joined        | Device identity exists ONLY in Azure AD      | Cloud-first, new devices        |
| Hybrid Azure AD Joined | Device in on-prem AD AND Azure AD           | Existing on-prem AD orgs        |
| Azure AD Registered    | Personal device with work account added      | BYOD, mobile devices            |

- In Azure AD, click "Devices" > "Device settings"
- Configure: who can join, require MFA, max devices per user

**Recommended Settings:**
- Users may join devices: Selected (specific groups)
- Require MFA to register devices: Yes
- Max devices per user: 20-50

---

## Part 1E: Configure Company Branding
### Why This Matters
Custom branding makes the login experience professional and helps prevent phishing.

- In Azure AD, click "Company branding" under "Manage"
- Click "Configure" (or "+ New language")
- Upload/configure: banner logo, background image, square logo, username hint, sign-in page text
- Advanced: remain signed in, background color, dark theme logo
- Click "Save" and test at https://login.microsoftonline.com

> **Exam Tip:** Company branding requires Premium licenses. You can configure different branding for different languages.

---

## Part 1F: Monitoring and Audit Logs
### Understanding Azure AD Monitoring
Azure AD tracks all activities: sign-ins, password resets, role assignments, etc.

- In Azure AD, click "Audit logs" under "Monitoring"
- Filter by date, service, category, activity, status
- Click "Sign-in logs" to review authentication attempts
- Important columns: User, Application, Status, IP, Location, Device info
- For advanced monitoring, configure Diagnostic settings to export logs to Log Analytics

> **Exam Tip:** Audit logs are kept for 30 days (Free), 90 days (P1). Exporting to Log Analytics extends retention.

---

## Lab 1 Verification Checklist
- [x] Navigate the Azure AD portal confidently
- [x] Understand tenant properties and cannot-change settings
- [x] Add and verify custom domains
- [x] Explain the difference between directory roles
- [x] Understand device join types
- [x] Configure company branding (with Premium license)
- [x] Access and filter audit logs

---

_Proceed to Lab 2 for user management and role assignments._
