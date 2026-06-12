# m365-tenant-hardening

I built a Microsoft 365 environment from scratch and deployed custom Conditional Access policies to secure the tenant. I blocked legacy authentication protocols, restricted foreign access, and enforced Multi-Factor Authentication across all accounts to create a secure identity baseline.

## Conditional Access Policy Architecture

### Policy Enforcement Matrix

| Policy Name | Target Assignment | Target Cloud Apps | Conditions / Signals | Access Controls Enforced |
| :--- | :--- | :--- | :--- | :--- |
| **Block Legacy Apps** | All Users | All Cloud Apps | Any Client Apps (IMAP, POP3, SMTP) | **Block Access** |
| **MFA Policy** | All Users | All Cloud Apps | Any Location | **Grant Access** <br> ↳ Requires MFA <br> ↳ Requires Microsoft Authenticator |
| **Block Foreign Policy** | All Users | All Cloud Apps | Geolocation (Outside designated operating countries) | **Block Access** |
