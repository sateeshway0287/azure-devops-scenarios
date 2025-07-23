# Monitoring, Logging & Alerting (Azure)
*Role: Site Reliability Engineer / DevOps Engineer*

---

## 1. End-to-End Monitoring Strategy in Azure
**Q:** How would you design a complete monitoring and alerting stack for a distributed application on Azure?

**A:**
- **Telemetry Collection:**
  - Application Insights (App-level)
  - Azure Monitor Agent (Infra-level)
- **Logging:**
  - Log Analytics Workspace
  - Diagnostic settings on all Azure resources
- **Alerting:**
  - Alerts in Azure Monitor (based on Log Analytics or Metrics)
  - Action Groups for emails, SMS, Logic Apps
- **Dashboards:**
  - Azure Workbooks for custom views
  - Azure Dashboard for central visibility
- **Best Practices:**
  - Enable distributed tracing with App Insights SDK
  - Use Kusto Query Language (KQL) for querying logs
  - Integrate alerts with ITSM or Teams/Slack

---

## 2. Handling Noisy Alerts
**Q:** How do you reduce false positives or alert fatigue in production?

**A:**
- Tune alert thresholds based on historical baselines
- Use Dynamic Thresholds in Azure Monitor
- Aggregate alerts using Action Rules
- Implement suppression rules for known maintenance windows
- Correlate incidents via Workbooks or external tools (e.g., PagerDuty)

---

## 3. Monitoring Containerized Workloads (AKS)
**Q:** How do you monitor Kubernetes workloads running in AKS?

**A:**
- Enable Azure Monitor for Containers
- Use Prometheus metrics via Azure Monitor managed service for Prometheus
- Collect logs via Fluent Bit or Container Insights
- Use KQL in Log Analytics to build dashboards
- Track pod restarts, CPU/memory limits, node health

---

## 4. Tracking SLA & Application Availability
**Q:** What tools do you use to ensure uptime and SLA compliance?

**A:**
- Azure Availability Tests (URL Ping / Multi-step)
- Application Map in App Insights
- Custom metrics (latency, request failure rate)
- Synthetic tests via Azure Monitor

---

## 5. Centralized Logging from Multiple Subscriptions
**Q:** How do you consolidate logs across multiple Azure subscriptions?

**A:**
- Create centralized Log Analytics workspace
- Configure Diagnostic Settings from all subscriptions to forward to this workspace
- Use Azure Lighthouse for access delegation
- Create cross-subscription dashboards with Azure Workbooks

---

## 6. Monitoring for Security & Compliance
**Q:** How do you ensure your logging setup helps meet compliance or security standards?

**A:**
- Enable Azure Activity Logs and forward to Log Analytics
- Enable Defender for Cloud with built-in recommendations
- Use Microsoft Sentinel for SIEM & SOAR
- Audit logs from Azure AD, Key Vault, Network Security Groups

---

## 7. Visualizing Data with Azure Dashboards
**Q:** What are the differences between Azure Dashboards and Workbooks?

**A:**
- **Azure Dashboards:** Lightweight, tile-based, global view
- **Azure Workbooks:** Interactive, multi-source, detailed diagnostics, supports parameters and KQL
- Use Workbooks for deep dives and Dashboards for executives/stakeholders

---

## 8. Alert Routing & Escalation Management
**Q:** How do you route critical alerts to the right people?

**A:**
- Define Action Groups with multiple notification channels (email, SMS, webhooks)
- Integrate with ITSM systems like ServiceNow
- Escalate via Logic Apps or webhook to Slack/Teams
- Use severity-based alerting strategy

---

## 9. Monitoring Serverless (Azure Functions)
**Q:** What do you monitor in Azure Functions?

**A:**
- Enable Application Insights (pre-integrated)
- Track cold starts, failed executions, performance bottlenecks
- Use custom telemetry if needed via ILogger
- Set up alerts on exception count, timeout metrics, and queue trigger failures

---

## 10. Proactive Monitoring Best Practices
**Q:** How do you stay ahead of issues instead of reacting after downtime?

**A:**
- Set up proactive health checks and synthetic transactions
- Automate remediation using Alerts + Logic Apps
- Review dashboards daily or weekly with SRE teams
- Implement auto-scaling based on monitored metrics
- Run chaos tests to validate alerting readiness

---

## 11. Detecting Configuration Drift via Monitoring
**Q:** How do you detect changes made outside Infrastructure-as-Code deployments?

**A:**
- Use Azure Change Tracking and Inventory
- Enable Defender for Cloud recommendations
- Compare actual vs expected configurations via policy compliance audits
- Alert on unauthorized changes to critical resources

---

## 12. Monitoring Logic Apps, API Management, and Event Grid
**Q:** How do you monitor integration workloads across Logic Apps and APIs?

**A:**
- Enable diagnostics for Logic Apps and APIM
- Stream logs to Log Analytics or Event Hub
- Monitor dead-letter queues and failed event subscriptions in Event Grid
- Set alerts for high error rates or throughput anomalies

---

## 13. Custom Metrics and Dimensions in Azure Monitor
**Q:** Can you create and use custom metrics for monitoring beyond built-in metrics?

**A:**
- Yes. Use Azure Monitor SDK or Application Insights TrackMetric API
- Emit business KPIs or application-specific metrics
- Aggregate via custom dimensions (e.g., user region, tenant ID)

---

## 14. Handling Monitoring for Hybrid and On-Prem Workloads
**Q:** How do you extend Azure monitoring to on-premises or hybrid infrastructure?

**A:**
- Install Azure Monitor Agent or Log Analytics agent on on-prem VMs
- Use Azure Arc to manage non-Azure servers
- Forward logs and metrics to central Azure Monitor environment