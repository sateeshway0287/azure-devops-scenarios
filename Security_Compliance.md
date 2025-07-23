# Security & Compliance (Azure)
*Role: Security Architect*

---

## 1. Designing a Secure Azure Environment
**Q:** How do you architect a secure Azure infrastructure for a regulated industry (e.g., finance, healthcare)?

**A:**
- **Network Isolation:** Use Azure Virtual Networks, NSGs, Azure Firewall
- **Zero Trust Model:** Enforce identity-aware access with Conditional Access
- **Privileged Access:** Use PIM (Privileged Identity Management) for just-in-time access
- **Encryption:** Enable encryption at rest (Azure Storage, SQL TDE) and in transit (TLS 1.2+)
- **Policy Enforcement:** Define Azure Policies and Blueprints to enforce guardrails
- **Security Center:** Enable Microsoft Defender for Cloud for threat detection and compliance

---

## 2. Enforcing Compliance Across Subscriptions
**Q:** How do you ensure all Azure subscriptions adhere to enterprise security standards?

**A:**
- Apply Azure Policy at Management Group level
- Use Azure Blueprints for consistent deployment of RBAC, Policies, and Templates
- Configure centralized security baselines via Defender for Cloud regulatory compliance templates
- Audit policy compliance via Azure Policy Insights

---

## 3. Managing Identity & Access in Azure
**Q:** What are best practices for identity and access management (IAM) in Azure?

**A:**
- Use Entra ID (Azure AD) for unified identity management
- Apply role-based access control (RBAC) using least privilege principle
- Implement Conditional Access policies
- Require MFA for all users, especially global admins
- Review access regularly using Access Reviews in Entra ID

---

## 4. Monitoring and Auditing for Security
**Q:** How do you monitor and audit security-related events across your Azure environment?

**A:**
- Enable Azure Activity Logs and forward to Log Analytics or Sentinel
- Enable audit logs for Entra ID (sign-ins, conditional access)
- Use Microsoft Sentinel for SIEM capabilities
- Set alerts on suspicious behavior (e.g., failed logins, privilege escalations)

---

## 5. Managing Secrets and Certificates
**Q:** How do you securely store and manage secrets, keys, and certificates?

**A:**
- Use Azure Key Vault
- Enable soft delete and purge protection
- Integrate with managed identities to avoid hard-coded secrets
- Rotate secrets periodically using Key Vault event triggers + automation

---

## 6. Threat Detection and Response
**Q:** What services do you use to detect threats and respond to incidents in Azure?

**A:**
- Microsoft Defender for Cloud (formerly ASC) for workload protection
- Microsoft Sentinel for incident correlation, investigation, and automation
- Enable Just-In-Time VM access to reduce exposure
- Configure security alerts to trigger Logic Apps for automated response

---

## 7. Data Loss Prevention (DLP) and Information Protection
**Q:** How do you prevent accidental or malicious data leakage in Azure?

**A:**
- Use Microsoft Purview for data classification and loss prevention policies
- Apply sensitivity labels to documents and emails
- Enforce Azure Information Protection (AIP) with integration into M365
- Enable eDiscovery and audit logging

---

## 8. Managing Secure DevOps
**Q:** How do you secure your CI/CD pipelines in Azure DevOps or GitHub?

**A:**
- Use service connections with least privilege
- Store secrets in Azure Key Vault and reference them in pipelines
- Enable branch protection, PR reviews, and commit signing
- Scan pipelines for vulnerabilities using Defender for DevOps
- Enforce infrastructure as code scanning (e.g., Bicep, Terraform policies)

---

## 9. Responding to Compliance Audits
**Q:** What tools help you prepare for or respond to external compliance audits?

**A:**
- Microsoft Defender for Cloud regulatory compliance dashboard
- Azure Policy and Compliance Manager (preview)
- Export policy compliance reports
- Use Microsoft Purview Risk & Compliance Portal for DLP and eDiscovery tracking

---

## 10. Best Practices for Secure Hybrid Connectivity
**Q:** How do you securely connect on-premise and Azure environments?

**A:**
- Use VPN Gateway or ExpressRoute with private peering
- Enforce firewall rules and custom DNS for name resolution
- Enable private endpoints for PaaS services
- Use Network Watcher and NSG Flow Logs for monitoring

---

## 11. Securing PaaS Services (e.g., App Service, Storage, SQL)
**Q:** How do you secure Platform-as-a-Service (PaaS) resources in Azure?

**A:**
- Use Private Endpoints to eliminate public access
- Apply NSG/Firewall rules at subnet/resource level
- Enforce managed identity authentication
- Enable Defender for PaaS-specific threat protection
- Audit logs and configure alerts for access changes

---

## 12. Incident Response and Playbooks
**Q:** How do you prepare your Azure environment for automated incident response?

**A:**
- Define incident response strategy using Microsoft Sentinel Playbooks (Logic Apps)
- Set alert triggers from Defender or Sentinel
- Automate actions: isolate VM, revoke tokens, notify SecOps
- Perform post-incident reviews using audit logs and investigation graphs

---

## 13. Third-Party Integration for Security Tools
**Q:** How can you integrate third-party security solutions with Azure?

**A:**
- Use Azure Event Hub or Log Analytics workspace as ingestion point
- Connect external SIEM tools to Sentinel via Data Connectors
- Use Defender for APIs and CASB capabilities for SaaS and external apps
- Configure Azure Marketplace solutions (e.g., Tenable, Qualys)

---

## 14. Handling Shadow IT and Unauthorized Usage
**Q:** How do you detect and mitigate use of unauthorized services in Azure?

**A:**
- Use Microsoft Defender for Cloud Apps (CASB)
- Monitor Azure Resource Graph and Activity Logs
- Enforce Azure Policy to block disallowed SKUs or services
- Educate teams through governance policies and FinOps alignment

---

## 15. Managing Secure Multi-Tenant Architectures
**Q:** What considerations are critical for securing multi-tenant SaaS on Azure?

**A:**
- Implement strong tenant isolation (data, network, identity)
- Use Azure AD B2C or Entra External ID for identity federation
- Enforce RBAC per tenant context
- Leverage Defender for Cloud for workload threat analytics
- Encrypt customer data with customer-managed keys (CMK)