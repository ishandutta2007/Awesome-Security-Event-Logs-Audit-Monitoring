# Awesome-Security-Event-Logs-Audit-Monitoring

# Awesome Security Event Logs & Audit Monitoring

> A curated list of top Security Event Logs and Audit Monitoring platforms — both SaaS/Hosted commercial solutions and open-source alternatives for centralizing logs, detecting threats, and maintaining audit trails.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Druva Security Events & Audit Trails](#druva-security-events--audit-trails)
  - [Datadog Cloud SIEM](#datadog-cloud-siem)
  - [Splunk Cloud Platform](#splunk-cloud-platform)
  - [Sumo Logic Cloud SIEM](#sumo-logic-cloud-siem)
  - [Microsoft Sentinel](#microsoft-sentinel)
  - [Coralogix](#coralogix)
- [Open-Source Software](#-open-source-software)
  - [Wazuh](#wazuh)
  - [Graylog](#graylog)
  - [OpenSearch](#opensearch)
  - [Grafana Loki](#grafana-loki)
  - [Retraced](#retraced)
  - [Auditum](#auditum)
  - [Fluentd](#fluentd)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Security Event Logs and Audit Monitoring platforms. These are not open-source but are included as reference points for feature comparison.

### Druva Security Events & Audit Trails
**Type:** Data protection-native security monitoring and audit trails  
Druva provides a **Security Events dashboard** that surfaces administrator login events, data access events, API requests, and unusual data activity alerts across all Druva products [citation:2]. It tracks new geo-locations for logins and API calls, restore and download activities, and quarantined endpoints, with the ability to expand the view from 7 to 30 days to spot anomalies [citation:2]. For audit trails, the **Admin Audit Trail** records detailed activity events (including PST conversion requests with download links), while **User Audit Trails** track end-user actions [citation:1]. Druva also exposes a **Cloud Platform Events API** for SIEM integration, with event types covering Admin Audit Trail, Admin Login, User Event, User Audit Trail, API Login, Backup, Restore, Download, and more, each with severity and identity type fields [citation:8].  
**Best for:** Druva customers wanting native security event visibility and audit trails for their data protection operations, with API access for SIEM integration.

### Datadog Cloud SIEM
**Type:** Cloud SIEM with log management and threat detection  
Datadog Cloud SIEM ingests logs from cloud providers, applications, and security tools, applying built-in detection rules and threat intelligence to surface security signals. It correlates logs with infrastructure metrics and traces for context-rich investigation. Pricing is module-based, scaling with log volume and security events.

### Splunk Cloud Platform
**Type:** Enterprise SIEM and log analytics  
Splunk is the long-standing enterprise standard for log management and SIEM, with schema-on-read indexing, SPL queries, and extensive security use case content. It is the canonical choice for large organizations with dedicated SOC teams and multi-year retention requirements. Pricing is based on data ingest volume.

### Sumo Logic Cloud SIEM
**Type:** Cloud-native SIEM with automated correlation  
Sumo Logic provides cloud-native log analytics and SIEM with automated anomaly detection, UEBA, and MITRE ATT&CK-mapped threat detection. It is positioned for organizations wanting a managed SIEM without infrastructure overhead.

### Microsoft Sentinel
**Type:** Cloud-native SIEM within Microsoft ecosystem  
Microsoft Sentinel is Microsoft's cloud-native SIEM and SOAR platform, deeply integrated with Azure, Microsoft 365, and the broader Microsoft security stack. It offers built-in connectors for Microsoft and third-party sources, analytics rules, and automation playbooks. Pricing is based on data ingestion and retention.

### Coralogix
**Type:** Full-stack observability with security analytics  
Coralogix provides log management, metrics, and tracing with security analytics capabilities, emphasizing predictable pricing and in-stream analysis without expensive indexing. Suited for teams wanting unified observability and security data in one platform.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Security Event Logs and Audit Monitoring tools. The open-source ecosystem spans **full SIEM platforms**, **log management backends**, **audit log services**, and **log collection pipelines**.

### Wazuh
**Stack:** C++ / OpenSearch | **License:** GPL-2.0  
Wazuh is the leading open-source security platform combining SIEM and XDR capabilities, with a Gartner Peer Insights rating of 4.4 stars across 57 reviews [citation:4]. It provides real-time threat detection, log analysis, file integrity monitoring, vulnerability detection, and active response. Reviewers highlight comprehensive threat detection, integration flexibility, and open-source customizability as key strengths [citation:4]. **Trade-off:** Documentation gaps exist, active response scripts are somewhat limited, and resource usage is high, primarily due to the Elasticsearch/OpenSearch backend [citation:4].  
**Best for:** Security teams wanting a comprehensive open-source SIEM with real-time alerting, compliance reporting, and the ability to tailor rules to specific needs, accepting the operational overhead of the OpenSearch backend.

### Graylog
**Stack:** Java / MongoDB / Elasticsearch/OpenSearch | **License:** GPLv3 (Open) / Commercial  
Graylog Open is a powerful self-managed log management platform with a free tier that many teams find sufficient. It provides centralized log collection, search, dashboards, and alerting. The paid Enterprise and Security editions add automation, compliance features, and Intelligent Data Management for routing lower-priority data to a data lake. Graylog is a practical choice for organizations wanting a proven log management platform without the full complexity of a SIEM.

### OpenSearch
**Stack:** Java / Lucene | **License:** Apache-2.0  
OpenSearch is the Apache-licensed fork of Elasticsearch and Kibana, providing log storage, search, and visualization through OpenSearch Dashboards [citation:14]. It is the backend for Wazuh and many other security tools. While not a SIEM on its own, it provides the scalable search and analytics foundation that security platforms build upon.  
**Best for:** Organizations wanting an Apache-licensed search and analytics backend for building custom log management and security analytics solutions.

### Grafana Loki
**Stack:** Go | **License:** AGPL-3.0  
Grafana Loki is a horizontally scalable, highly available log aggregation system inspired by Prometheus. It indexes only metadata (labels) rather than the full text of logs, making it significantly cheaper to operate than full-index solutions. It integrates natively with Grafana for visualization and alerting, and is commonly used for security event correlation alongside Prometheus metrics.  
**Best for:** Teams already using Grafana and Prometheus wanting cost-efficient log aggregation with label-based indexing and native Grafana integration.

### Retraced
**Stack:** Node.js / PostgreSQL / Kubernetes | **License:** Open Source  
Retraced is a fully open-source **audit logs service with an embeddable UI**, designed to integrate compliant audit logging into applications [citation:5]. It provides a searchable, exportable record of read/write events, with client libraries for Go and JavaScript [citation:5]. It deploys via Docker Compose or Kubernetes (Skaffold), and includes a Logs Viewer example and Admin Portal [citation:5]. Unlike full SIEM platforms, Retraced focuses specifically on application-level audit trails.  
**Best for:** Developers wanting to embed compliant audit logging into their own applications without building the infrastructure from scratch, particularly for SaaS products needing SOC 2-style audit trails.

### Auditum
**Stack:** Go / Cloud-native | **License:** Apache-2.0  
Auditum is an audit trail management system for collecting, storing, and querying audit records across multiple applications in one place [citation:10]. It is cloud-native, API-first (HTTP and gRPC), and designed to integrate with business applications [citation:10]. It includes built-in observability (logging, metrics, tracing) and is developer-friendly for easy configuration [citation:10].  
**Best for:** Engineering teams wanting a dedicated, API-driven audit log backend for their applications, with cloud-native deployment and multi-application support.

### Fluentd
**Stack:** Ruby / C | **License:** Apache-2.0  
Fluentd is an open-source log collector and router designed to unify log ingestion across heterogeneous infrastructure [citation:9]. It accepts log events from sources, buffers them locally, applies parsing and filtering, and routes to destinations like Elasticsearch, Splunk, or cloud SIEMs [citation:9]. **Important:** Fluentd does not store or analyze logs—it is the collection layer, not a SIEM [citation:14]. For Kubernetes environments, Fluent Bit is often preferred as a lighter-weight alternative (~4 MB binary vs. Fluentd's Ruby-based process) [citation:9].  
**Best for:** Teams needing a reliable, plugin-rich log collection and forwarding layer in front of their storage or SIEM backend, particularly with complex routing requirements.

---

## 📊 Comparison at a Glance

| Software | License | Stack | SIEM Capabilities | Audit Focus | Self-Hosted | Best For |
|----------|---------|-------|-------------------|-------------|-------------|----------|
| **Druva** | Proprietary | Cloud | (Security Events) | ✅ Native | ❌ | Druva data protection audit |
| **Datadog SIEM** | Proprietary | Cloud | ✅ | (Logs) | ❌ | Cloud SIEM + observability |
| **Splunk** | Proprietary | Cloud/On-prem | ✅ | (Logs) | (On-prem) | Enterprise SIEM |
| **Microsoft Sentinel** | Proprietary | Cloud | ✅ | (Logs) | ❌ | Microsoft ecosystem SIEM |
| **Wazuh** | GPL-2.0 | C++/OpenSearch | ✅ Full | ✅ (FIM, rules) | ✅ | Open-source SIEM + XDR |
| **Graylog** | GPLv3 (Open) | Java/Mongo/OS | (Security edition) | (Logs) | ✅ | Log management + alerting |
| **OpenSearch** | Apache-2.0 | Java | ❌ (Backend) | ❌ | ✅ | Search backend |
| **Grafana Loki** | AGPL-3.0 | Go | (Via Grafana) | ❌ | ✅ | Cost-efficient log aggregation |
| **Retraced** | Open Source | Node.js/Postgres | ❌ | ✅ Embeddable | ✅ | Application audit logs |
| **Auditum** | Apache-2.0 | Go | ❌ | ✅ API-first | ✅ | Multi-app audit backend |
| **Fluentd** | Apache-2.0 | Ruby | ❌ (Collector) | ❌ | ✅ | Log collection + routing |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Security Event Logs or Audit Monitoring tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem **splits** between **full SIEM platforms** (Wazuh, the most comprehensive open-source security platform with 4.4-star Gartner rating [citation:4]), **log management backends** (Graylog, OpenSearch, Grafana Loki), **application audit services** (Retraced, Auditum), and **collection pipelines** (Fluentd). **Wazuh** is the strongest choice for security event monitoring with built-in detection rules and active response, while **Retraced** and **Auditum** fill the specific need for embeddable application-level audit trails. Commercial platforms like Splunk and Microsoft Sentinel remain the enterprise standard for large SOC operations, while Druva provides native audit trails for its data protection ecosystem [citation:2][citation:8].

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
