# Infrastructure as Code (IaC)
*Role: Cloud Engineer / DevOps Engineer*

## 1. Designing IaC for Multi-Environment Azure Setup
**Q:** How do you organize Terraform or Bicep code for Dev, UAT, and Prod in Azure?

**A:**
- Use a modular directory structure: `/modules` and `/env/dev`, `/env/prod`.
- Leverage environment-specific variable files (`*.tfvars` or parameter files).
- Implement remote state using Azure Storage + state locking with Azure Cosmos DB or Blob leases.

## 2. Secrets in IaC Templates
**Q:** How do you handle secrets like connection strings or credentials in your IaC deployments?

**A:**
- Reference secrets from Azure Key Vault using data sources (Terraform) or secure parameter references (Bicep).
- Avoid hardcoded values; enforce scanning using `tfsec`, `checkov`.

## 3. Reusability & DRY Principles
**Q:** How do you ensure reusability and avoid duplication in IaC?

**A:**
- Define reusable modules with clear input/output.
- Use version-controlled module registry (Git or private Terraform registry).
- Apply naming and tagging conventions via variables.

## 4. Blueprints vs ARM vs Bicep vs Terraform
**Q:** Which tool would you choose and why?

**A:**
- **Terraform:** Community-rich, multi-cloud, modular, and production-proven.
- **Bicep:** Native Azure support, secure and transparent (recommended for all new Azure-native IaC).
- **ARM Templates:** JSON-based, verbose; use when Bicep isn't supported.
- **Blueprints:** Deprecated; use Bicep/Policy combination now.

## 5. Policy-as-Code Integration
**Q:** How do you enforce governance controls via IaC?

**A:**
- Use `azurerm_policy_definition` and `azurerm_policy_assignment` (Terraform).
- Define policies for allowed SKUs, regions, tagging, Key Vault usage.
- Enforce with initiative definitions and Management Groups.

## 6. Version Control & CI Integration
**Q:** How do you manage IaC in pipelines?

**A:**
- Store code in Git (Azure Repos or GitHub).
- Run `terraform plan` in PR builds and require manual approval for `apply`.
- Use Azure DevOps pipelines or GitHub Actions with stages: Init > Validate > Plan > Apply.

## 7. Drift Detection
**Q:** How do you detect changes made outside IaC?

**A:**
- Use `terraform plan` and compare state regularly.
- Integrate drift detection tools like Terraform Cloud or third-party modules.
- Enforce role restrictions on Azure to prevent portal drift.

## 8. Secure State Management
**Q:** How do you securely manage Terraform state files?

**A:**
- Store state in Azure Blob with private access.
- Enable soft delete and versioning on storage.
- Use backend config with access via RBAC + service principal identity.

## 9. Dynamic Resource Creation
**Q:** How do you handle condition-based resource creation?

**A:**
- Use `count`, `for_each`, and conditional logic in Terraform.
- In Bicep, use conditional deployment blocks and `if` expressions.
- Always document the rationale behind toggles.

## 10. Infrastructure Testing & Validation
**Q:** How do you validate infrastructure deployment?

**A:**
- Run `terraform validate`, `tflint`, `checkov`, and `infracost`.
- For functional tests, use `Terratest`, `Pester` (PowerShell), or deployment scripts with validation steps.
- Post-deployment validation with Azure Monitor alerts and compliance scans.
