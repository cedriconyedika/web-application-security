# Identity and Authentication Policy
## Enterprise Security Framework

**Version:** 1.0  
**Effective Date:** January 2026  
**Classification:** Internal Use Only  
**Document Owner:** Information Security Team  
**Approved By:** Chief Information Security Officer (CISO)  
**Next Review Date:** January 2027  

---

## 1. Purpose

This policy establishes mandatory requirements for the creation, management, protection, and monitoring of digital identities and authentication credentials across the organization.  

The objective is to reduce the risk of unauthorized access, credential compromise, privilege abuse, and lateral movement within enterprise systems while maintaining the confidentiality, integrity, and availability of organizational assets.  

This policy aligns with guidance from the Digital Identity Guidelines (SP 800-63B) and access control principles defined by ISO/IEC 27001.

---

## 2. Scope

This policy applies to:

- All employees, contractors, vendors, and third parties with access to organizational systems.
- All on-premises infrastructure.
- All cloud platforms and SaaS applications.
- All endpoints accessing company resources.
- All remote access mechanisms, including VPN and Zero Trust Network Access (ZTNA).

---

## 3. Definitions

**Password** – A knowledge-based authentication secret used to verify identity.  

**Passphrase** – A longer password composed of multiple words that provides increased entropy and resistance to brute-force attacks.  

**Multi-Factor Authentication (MFA)** – Authentication requiring two or more independent factors: something the user knows, has, or is.  

**Privileged Account** – An account with elevated permissions capable of modifying system configurations or accessing sensitive data.  

**Principle of Least Privilege** – Users are granted only the minimum access required to perform assigned duties.  

---

## 4. Policy Requirements

### 4.1 Password Creation

- Standard user passwords must be a minimum of 12 characters.
- Privileged account passwords must be a minimum of 14 characters.
- Passphrases are strongly encouraged.
- Passwords must not contain easily guessable information such as names, usernames, or company identifiers.
- The system must block commonly used, breached, or previously used passwords.
- Organizational passwords must not be reused for personal accounts.
- Mandatory complexity rules (e.g., forced symbols or uppercase characters) are not required unless technically mandated by legacy systems.

---

### 4.2 Password Storage

- Passwords must never be stored in plaintext or reversible encryption formats.
- All passwords must be hashed using a salted, memory-hard algorithm.
- Approved hashing algorithms include Argon2id (preferred), bcrypt, or PBKDF2 with appropriate iteration counts.
- Legacy hashing algorithms such as MD5 or SHA-1 are prohibited.
- Passwords must not be logged, emailed, or stored in internal messaging platforms.

---

### 4.3 Password Transmission

- All authentication traffic must use TLS 1.2 or higher.
- Transmission of credentials over unencrypted protocols (HTTP, FTP, Telnet) is prohibited.
- Systems must validate certificates against trusted certificate authorities.
- Self-signed certificates are prohibited in production environments unless formally approved.

---

### 4.4 Multi-Factor Authentication (MFA)

MFA is mandatory for:

- All remote access.
- All cloud services.
- All privileged accounts.
- Access to sensitive data repositories.

Security key–based authentication (FIDO2/WebAuthn) is preferred.  

Application-based authenticators are acceptable.  

SMS-based MFA is an exception-only and permitted only as a fallback mechanism.

---

### 4.5 Password Reset and Rotation

- Routine periodic password expiration is not required.
- Password changes are required upon:
  - Suspected or confirmed compromise.
  - Detection of anomalous login activity.
  - Significant role or privilege change.
  - Instruction from the Information Security team.

---

### 4.6 Account Lockout Controls

- User accounts are locked after 5 failed login attempts within 15 minutes.
- Privileged accounts are locked after 3 failed attempts.
- Lockout events must be logged and monitored by the Security Operations function.
- Repeated failed attempts across accounts from a common source must trigger investigation.

---

### 4.7 Privileged Account Management

- Administrative users must maintain separate standard and privileged accounts.
- Shared administrative credentials are prohibited.
- Privileged access must follow least privilege principles.
- Where feasible, privileged access should be time-bound and automatically revoked.
- Administrative activities must be logged for audit purposes.

---

### 4.8 Password Manager Usage

- Employees must use the organization-approved password manager for storing business credentials.
- Password manager access must be protected with MFA.
- Master passphrases must be unique and at least 16 characters in length.
- Credentials must not be stored in unsecured documents or browser-based plaintext storage.

---

## 5. Responsibilities

### 5.1 Users

Users must:

- Protect authentication credentials from disclosure.
- Immediately report suspected compromise.
- Complete required security awareness training.
- Comply with MFA and password requirements.

---

### 5.2 IT and Security Teams

The IT and Information Security teams must:

- Enforce technical controls defined in this policy.
- Monitor authentication events and investigate anomalies.
- Provision and deprovision accounts promptly.
- Conduct periodic access reviews.
- Review and update this policy annually.

---

## 6. Compliance and Enforcement

Compliance with this policy is mandatory.

Violations may result in:

- Mandatory retraining
- Suspension of system access
- Disciplinary action up to and including termination
- Contract termination for third parties

The organization reserves the right to immediately suspend access to any account suspected of compromise or non-compliance.

---

## 7. Exceptions

Exceptions must:

- Be submitted in writing.
- Include documented business justification.
- Include a formal risk assessment.
- Be approved by the Chief Information Security Officer (CISO).
- Be reviewed at least annually.

Compensating controls must be implemented for all approved exceptions.

---

## 8. Review and Maintenance

This policy will be reviewed annually or upon:

- Major security incidents.
- Regulatory changes.
- Significant technology changes.

All revisions require executive approval.
