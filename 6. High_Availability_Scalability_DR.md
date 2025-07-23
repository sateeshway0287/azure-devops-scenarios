# High Availability, DR & Scalability (Azure)
*Role: Cloud Architect*

---

## 1. Designing Highly Available Solutions
**Q:** How do you ensure high availability for Azure-hosted workloads?

**A:**
- Deploy across multiple Availability Zones or Availability Sets
- Use Azure Load Balancer or Application Gateway for traffic distribution
- Choose Zone-redundant services (e.g., Azure SQL, Azure Storage)
- Configure auto-healing for web apps and VMs

---

## 2. Choosing the Right Azure Regions
**Q:** What factors influence your selection of Azure regions for deployment?

**A:**
- Proximity to users (latency-sensitive apps)
- Regulatory compliance and data residency
- Availability of required services (not all SKUs are global)
- Multi-region pairing for disaster recovery

---

## 3. Implementing Disaster Recovery (DR)
**Q:** What Azure-native tools help you implement DR for critical workloads?

**A:**
- Azure Site Recovery for VM replication across regions
- Geo-redundant storage (GRS) or RA-GRS for data
- Azure SQL Auto-failover Groups
- Azure Traffic Manager for DNS-based failover

---

## 4. Ensuring Scalability under Load
**Q:** How do you ensure applications scale based on usage?

**A:**
- Enable Autoscale for App Service Plans and Virtual Machine Scale Sets
- Use Azure Kubernetes Service (AKS) with Horizontal Pod Autoscaler
- Monitor metrics via Azure Monitor and trigger scaling rules
- Adopt stateless design and use Azure Queue/Service Bus for buffering

---

## 5. Geo-Replication and Business Continuity
**Q:** How do you ensure business continuity with minimal downtime?

**A:**
- Deploy active-active or active-passive topology
- Use geo-replicated databases (Cosmos DB, SQL DB)
- Implement failover strategy with Azure Front Door or Traffic Manager
- Define RTO and RPO objectives; test DR plans regularly

---

## 6. Multi-Region Application Architecture
**Q:** What does a scalable multi-region architecture on Azure look like?

**A:**
- App Services or AKS in multiple regions
- Azure Front Door for global HTTP(S) routing
- Centralized or geo-distributed data layer (Cosmos DB, Azure SQL)
- Replicate secrets via Key Vault with soft delete & purge protection

---

## 7. Resilient Data Architecture
**Q:** How do you design data tiers to withstand failures?

**A:**
- Use Azure SQL with zone redundancy or failover groups
- Enable backups with long-term retention (LTR)
- Use Cosmos DB multi-region write capabilities
- Apply retry logic in application code

---

## 8. Application Gateway vs Front Door
**Q:** When should you use Azure Front Door vs Application Gateway?

**A:**
- **Azure Front Door:** Global routing, CDN, WAF, SSL offloading, latency-based
- **App Gateway:** Regional, layer 7 load balancer, WAF, session affinity
- Combine both for hybrid scenarios (Front Door for global entry, AGW for internal routing)

---

## 9. Auto-Healing and Self-Healing Applications
**Q:** How can applications recover from transient or infrastructure failures?

**A:**
- Enable auto-heal for App Services (e.g., recycle on memory leaks)
- Use Azure Monitor alerts to trigger Logic Apps for healing
- Add retry, timeout, and circuit breaker patterns in code
- Use AKS readiness/liveness probes for pod health

---

## 10. SLA-Aware Architecture Design
**Q:** How do you ensure SLA commitments are met?

**A:**
- Choose services with financially-backed SLAs (e.g., 99.99%)
- Distribute across zones to mitigate regional failures
- Monitor SLA-impacting events using Service Health and Alerts
- Document SLAs for internal and external customers
