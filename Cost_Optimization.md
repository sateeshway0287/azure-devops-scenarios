# Cost Optimization (Azure)
*Role: FinOps / Cloud Architect*

---

## 1. Cost Management Fundamentals
**Q:** How do you track and manage costs in Azure?

**A:**
- Use Azure Cost Management + Billing to view, forecast, and analyze spend
- Set budgets and configure alerts per subscription or resource group
- Enable cost allocation tags (e.g., app, environment, cost center)
- Review usage anomalies and trends weekly

---

## 2. Budget Alerts and Spend Control
**Q:** How do you ensure teams stay within budget?

**A:**
- Define Azure Budgets per team/project
- Set up cost alerts (email, webhook, action group)
- Use Management Groups to enforce spending policies across subscriptions
- Lock or restrict expensive SKUs using Azure Policy

---

## 3. Rightsizing and Reserved Instances
**Q:** How do you optimize VM and compute costs?

**A:**
- Analyze usage with Azure Advisor to identify underutilized VMs
- Apply resizing recommendations (e.g., Standard to B-Series)
- Purchase Reserved Instances or Savings Plans for predictable workloads
- Use auto-shutdown for dev/test environments

---

## 4. Storage Cost Optimization
**Q:** How do you reduce Azure storage costs?

**A:**
- Move infrequently accessed data to Cool/Archive tiers
- Enable lifecycle management policies to auto-transition blobs
- Delete stale snapshots and orphan disks
- Use Azure Files with Premium tier only when needed

---

## 5. Serverless and Consumption-Based Models
**Q:** How do serverless services help with cost savings?

**A:**
- Pay only for execution time (e.g., Azure Functions, Logic Apps)
- Eliminate idle compute charges
- Use Event Grid for event-driven architecture to avoid polling costs
- Scale dynamically without overprovisioning

---

## 6. Optimizing PaaS Services
**Q:** How can you optimize costs with Azure App Services, SQL DB, etc.?

**A:**
- Choose elastic pools for Azure SQL to share DTUs/vCores
- Use scale-to-zero where supported (e.g., Azure Container Apps)
- Apply autoscale to App Services
- Monitor with Azure Monitor to avoid overprovisioning

---

## 7. Network Egress and Bandwidth Considerations
**Q:** How do you minimize data transfer costs?

**A:**
- Prefer same-region communication to avoid egress charges
- Use Private Endpoints instead of public IPs for internal services
- Use Azure CDN to cache content closer to users
- Compress payloads and optimize API design

---

## 8. Cost Optimization in Dev/Test Environments
**Q:** What are some ways to reduce costs in non-production workloads?

**A:**
- Use Azure Dev/Test subscriptions with special pricing
- Schedule auto-start/stop of resources using Automation or Logic Apps
- Use B-Series VMs for intermittent workloads
- Clean up stale resources using resource cleanup policies

---

## 9. Governance & Cost Guardrails
**Q:** How do you ensure long-term cost governance?

**A:**
- Enforce naming/tagging standards via Azure Policy
- Use Management Groups for policy inheritance
- Integrate with FinOps dashboards for executive visibility
- Regular reviews of Azure Advisor recommendations

---

## 10. Cost Visibility Across Multi-Tenant / Business Units
**Q:** How do you provide cost visibility to different business units or tenants?

**A:**
- Use cost allocation tags and Resource Groups per BU
- Create custom dashboards in Azure Cost Management
- Enable Cost Analysis filters for scoped views
- Export usage data to storage or Power BI for detailed reporting