# CI/CD Pipeline & Automation (Azure)
*Role: DevOps Engineer*

## 1. Automated CI/CD Pipeline for Microservices (Docker)
**Q:** How would you design a pipeline using Azure DevOps (Repos, Pipelines, Artifacts, ACR)? What are your testing strategies and release control?

**A:**
- **CI/CD Tools:** Azure Repos, Pipelines, ACR.
- **Testing:** YAML for unit, integration, and E2E tests.
- **Controls:** Environments, approvals, and gated releases.
- **Best Practices:**
  - Least privilege service connections
  - Secrets in Key Vault
  - Dev → UAT → Prod rings

## 2. Migrating from Jenkins to Azure DevOps
**Q:** What is your migration strategy, and which services in Azure would replace Jenkins functionalities?

**A:**
- **Strategy:** Break down Jenkins pipelines into modular Azure DevOps YAML templates.
- **Mapping:**
  - Jenkins → Azure Pipelines
  - Jenkinsfile → YAML pipelines
  - Plugins → Marketplace tasks
- **Best Practices:** Incremental migration, reuse templates, phased cutover.

## 3. Hotfix Deployment with Bypass Capability
**Q:** How do you enable rapid hotfix deployment while maintaining controls?

**A:**
- Use a dedicated hotfix pipeline with manual approval gates.
- Deploy directly to prod with traceability (build tags, notes).
- Enable alerting & audit logging via Azure Monitor.

## 4. Optimize CI/CD for Frequent Small Changes
**Q:** How do you reduce pipeline execution time when many commits are pushed daily?

**A:**
- Use path-based triggers to run partial builds.
- Parallel testing with matrix strategy.
- Cache tools and Docker layers for reuse.

## 5. Blue/Green Deployment on Azure App Services or VMs
**Q:** How do you minimize downtime during deployments?

**A:**
- Use App Service deployment slots with swap.
- On VMs: leverage Load Balancer + pre-provisioned targets.
- Validate with App Insights. Roll back using re-swap or health checks.

## 6. Canary Releases for Azure Functions & API Management
**Q:** How to implement staged rollout for serverless?

**A:**
- Deployment slots for Function Apps.
- Gradual traffic routing via Front Door or API Management revisions.
- Monitor success rate via App Insights and auto-revert on failure.

## 7. Role-Based Access & Secrets Management
**Q:** How do you ensure secure access to pipelines and secrets?

**A:**
- Role-specific Azure DevOps groups + RBAC.
- Use Key Vault-integrated variable groups.
- Monitor access with Azure Monitor and Defender for DevOps.

## 8. GitHub Integration in Azure DevOps Pipelines
**Q:** How do you securely integrate GitHub with Azure DevOps?

**A:**
- Create secure GitHub service connection (PAT or OAuth).
- Apply branch policies and signed commits.
- Trigger CI from PR/merge using GitHub webhooks.

## 9. Integrating Security Scans into CI/CD
**Q:** Where and how should security scanning tools be integrated?

**A:**
- Inject scanning tools post-build: SonarCloud, Defender for DevOps, etc.
- Enforce gates for critical vulnerabilities.
- Automate reports into build artifacts.

## 10. Artifact Storage & Lifecycle Management
**Q:** How do you manage large build artifacts efficiently?

**A:**
- Use Azure Artifacts for packages or Blob Storage for binaries.
- Define naming and versioning conventions.
- Apply Azure Storage lifecycle policies to auto-tier/archive.
