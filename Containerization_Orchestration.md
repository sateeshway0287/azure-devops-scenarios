# Containerization & Orchestration (Azure)
*Role: DevOps Engineer / Platform Engineer*

---

## 1. Container Services in Azure
**Q:** What container orchestration options does Azure provide?

**A:**
- Azure Kubernetes Service (AKS) – fully managed Kubernetes
- Azure Container Apps – serverless containers with built-in scaling
- Azure App Service for Containers – simplified PaaS hosting
- Azure Container Instances (ACI) – ephemeral, single-container workloads

---

## 2. Azure Kubernetes Service (AKS) Fundamentals
**Q:** What are the key components and best practices for AKS?

**A:**
- Use node pools for workload isolation (e.g., system vs user)
- Enable Azure CNI for advanced networking
- Enable RBAC and integrate with Azure AD
- Use managed identity for workloads
- Monitor using Azure Monitor for Containers

---

## 3. Container Image Management
**Q:** How do you manage container images securely and efficiently in Azure?

**A:**
- Use Azure Container Registry (ACR)
- Enable image scanning with Microsoft Defender for Cloud
- Use ACR Tasks for automation and patching
- Enforce RBAC and Private Link access

---

## 4. CI/CD for Containers
**Q:** How do you automate container build and deployment in Azure?

**A:**
- Use GitHub Actions or Azure Pipelines for CI/CD
- Integrate with ACR and AKS using service connections
- Use Helm or Kustomize for manifest templating
- Leverage ArgoCD or Flux for GitOps model (optional)

---

## 5. Scaling Containers in AKS
**Q:** What are scaling strategies for containerized workloads?

**A:**
- Enable Horizontal Pod Autoscaler (HPA)
- Use KEDA for event-driven auto-scaling
- Configure Cluster Autoscaler for VM pool scaling
- Use Spot node pools for cost efficiency

---

## 6. Security Best Practices in Containers
**Q:** How do you secure workloads in AKS and containers in general?

**A:**
- Run containers as non-root user
- Scan base images for vulnerabilities
- Apply PodSecurityPolicies or Azure Policy for AKS
- Isolate workloads via namespaces and network policies
- Enable Defender for Containers for runtime protection

---

## 7. Monitoring & Observability in AKS
**Q:** What tools help monitor containerized apps in Azure?

**A:**
- Azure Monitor for Containers
- Container insights for performance and health
- Prometheus + Grafana for custom metrics
- Fluent Bit or Azure Monitor Agent for log forwarding

---

## 8. Multi-Tenant AKS Cluster Design
**Q:** What are key considerations for multi-tenant AKS clusters?

**A:**
- Use namespaces and resource quotas to isolate workloads
- Apply Azure AD integration with Kubernetes RBAC
- Leverage network policies to restrict intra-tenant traffic
- Use Gatekeeper or Azure Policy for policy enforcement

---

## 9. AKS Networking Options
**Q:** What are common AKS networking models and use cases?

**A:**
- Kubenet – simpler, smaller IP footprint
- Azure CNI – full VNet integration, suitable for enterprise
- Bring your own CNI (Cilium, Calico) – for advanced use cases
- Enable DSR, UDRs, and private ingress as needed

---

## 10. Best Practices for AKS Upgrades and Lifecycle Management
**Q:** How do you manage lifecycle and upgrades in AKS?

**A:**
- Use node image auto-upgrade or manually rotate node pools
- Schedule maintenance windows
- Backup state (e.g., etcd, app configs)
- Test upgrades in staging first, monitor with health probes