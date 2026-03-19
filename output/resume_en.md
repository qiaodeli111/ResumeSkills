# DELI QIAO

+86 155-2201-3699 | qiaodeli111@126.com | Shenzhen, China | [github.com/qiaodeli111](https://github.com/qiaodeli111)

---

## Professional Summary

Senior DevOps/SRE engineer with 14 years of experience in infrastructure automation and platform engineering. Architected full-stack IaC systems spanning bare-metal (BMaaS), private cloud (CloudStack), and multi-cloud environments (AWS / Alibaba Cloud / Huawei Cloud / ChinaTelecom Cloud). Engineered a custom multi-cloud Terraform Provider in Go and led end-to-end domestication of Anolis OS ARM, UOS (Hygon C86), and OpenEuler platforms across x86/ARM64/C86 architectures. Holds AWS SAA, CKA, RHCE, Azure Admin, and PMP certifications.

---

## Technical Skills

| Category | Technologies |
|---|---|
| **Cloud Platforms** | CloudStack · AWS · Alibaba Cloud · Huawei Cloud · ChinaTelecom Cloud · Proxmox VE |
| **Container Orchestration** | Kubernetes · Docker · Helm · Harbor · JFrog Artifactory |
| **IaC & Automation** | Terraform (custom Provider) · Ansible · Packer · Tinkerbell · cloud-init |
| **Storage** | ZFS · DRBD · Linstor · LVM · Corosync/Pacemaker |
| **Networking** | L4/L7 LB · BGP · VLAN · OVS/DPDK · PXE/iPXE · Redfish |
| **Observability** | Grafana · Prometheus · Loki · Fluentd · Zabbix |
| **Security & Compliance** | Vault · Nessus · Lynis · Consul ACL · SSL/TLS · Trivy |
| **CI/CD** | GitLab CI · Jenkins · Goss · Ansible Tower |
| **Operating Systems** | Ubuntu · Anolis OS · UOS · OpenEuler · Windows (x86/ARM64/C86) |
| **Languages** | Go · Python · Shell/Bash · HCL |

---

## Professional Experience

### Shenzhen JetDev Technology Co., Ltd. — DevOps Team Lead & Delivery Efficiency Expert
**Oct 2024 – Present | Shenzhen, China**

Orchestrated 7 parallel projects simultaneously (BMaaS, Terraform, Image Factory, CloudStack, K8s, IT Infrastructure, JetDev), driving technical architecture and delivering across 5+ customer sites.

**Platform Engineering**

- Spearheaded development of JetDev, an all-in-one DevOps toolbox integrating Ansible, Terraform, Packer, and GitLab Runner; reduced Ansible Role project scaffolding time by **80%** and established a fully traceable workflow from code review to production deployment, adopted across operations and QA teams.
- Engineered a unified multi-cloud Terraform Provider in Go, supporting AWS, Alibaba Cloud, Huawei Cloud, and ChinaTelecom Cloud; implemented CloudStack resource orchestration via AWS-compatible API, eliminating multi-cloud configuration fragmentation and achieving "write once, run anywhere" IaaS provisioning.
- Architected and delivered a CloudStack private cloud platform on ZFS + Linstor distributed storage (DRBD 9.3.0) and VLAN advanced networking; completed **13 core feature deliveries**; boosted ZFS IOPS from **230k to ~800k** on PCIe 5.0 (32-core) through performance tuning; resolved DRBD heartbeat parameter issues to achieve **24/7 stable operation**; deployed Grafana dashboards for real-time CPU/memory/storage/IP utilization visibility.

**Automation Systems**

- Redesigned the automated image factory (Packer) to support a full matrix of **5 OS types** (Ubuntu / UOS / Anolis OS / OpenEuler / Windows) × **3 architectures** (x86_64 / ARM64 / C86); integrated Goss smoke testing and Lynis security auditing; improved concurrent build throughput by **3.2×**, maintained zero pipeline failures for **30+ consecutive days**, and completed **12 image delivery tasks**.
- Engineered deep enhancements to the BMaaS bare-metal provisioning platform: added automatic disk selection, multi-NIC dynamic bonding, pluggable HookOS driver framework, Rescue mode, and offline provisioning; delivered end-to-end OS deployment for a new Yangzhou Telecom site across x86/ARM64/C86; shipped the redfish-batch-iso tool for concurrent ISO bulk mounting.
- Designed and deployed multiple GitLab CI/CD pipelines: full-chain image factory automation (build / push / notification); Ansible "commit-to-test" pipeline (dynamic VM spin-up for deployment and idempotency verification); IaC MR approval workflow enabling automated, auditable cloud resource provisioning.

**Domestication & Storage Performance**

- Led full-stack adaptation for domestic OS platforms: completed Anolis OS 8 ARM JetIce image packaging (including HA stack: ZFS / DRBD / Corosync / Pacemaker integration); validated ZFS module compilation on UOS (Hygon C86) and OpenEuler; enabled standardized delivery across multiple domestic platforms.
- Directed storage performance engineering: designed and executed fio benchmark suites across **6 test scenarios** (random read/write, sequential read/write, mixed workloads; PCIe 3.0 vs 5.0 comparison); produced attributable performance reports; completed ZFS thin-provisioning evaluation and Linstor replica migration strategy validation.
- Delivered L4/L7 load balancer performance testing: executed full test case matrix, aggregated data, and published cross-team performance reports; completed L4LB containerization to Docker and BGP dynamic routing migration.

**Customer Delivery & Technical Support**

- Led multi-site customer delivery and on-site troubleshooting: root-caused network packet loss at Aerospace Institute JetIce deployment (NIC driver / kernel parameters / DPDK / OVS); remediated **6 critical CVEs** at Xiamen Telecom (including CVE-2023-27350) with confirmed re-test pass; achieved full-site Consul ACL security baseline compliance and L4LB containerization at Jishan Digital Living; redeployed inspection tooling at Panzhihua, Sichuan; integrated Wuxi Zabbix alerts into the Lingxiao platform.
- Orchestrated company-wide network infrastructure overhaul: full IP inventory and ownership mapping, VLAN segmentation, DNS/DHCP policy deployment, IPv4 address pool standardization; delivered **19 IT infrastructure tasks**.
- Drove K8s cluster platformization: validated Cluster API + CloudStack feasibility, defined "K8s on CloudStack + external LB + shared storage" architecture; planned Velero + MinIO backup and disaster recovery drills; migrated JumpServer to K8s via Helm Chart and upgraded to production SSL certificates.

---

### Kyndryl Shenzhen (IBM Spin-off) — SRE Engineer, Toolchain
**Sep 2021 – Aug 2024 | Shenzhen, China**

### IBM Shenzhen — SRE Engineer, Toolchain
**Mar 2017 – Sep 2021 | Shenzhen, China**

- Achieved "Exceeds Expectations" performance rating for **6 consecutive years**; managed cross-cultural teams of **4–10 engineers** across China and India.
- Built a comprehensive operations automation framework: improved team efficiency by **50%+**, elevated operations quality by **90%+**, reduced application deployment time by **80%**, and cut change request processing time by **50%+**.
- Administered full DevOps toolchain (Chef / GitLab / Jenkins / Ansible Tower / UCD); developed shared Ansible and Chef base libraries for business SRE teams.
- Served on the **AWS Architecture Advisory Team**: re-architected a client's global ECS monolith into an EKS cluster deployment, introduced AWS Global Accelerator for traffic distribution, and decoupled storage and database layers to resolve cross-region latency and cost issues.

---

### Tianjin En'en Technology Co., Ltd. — Change Service Delivery Manager
**May 2016 – Mar 2017**

- Automated change management processes using Excel macros and scripts, reducing team workload by **80%** and enabling fully automated monthly reporting.

---

### DXC Technology — WebHosting Team Lead / Operations Engineer
**Jun 2012 – May 2016**

- Led a **4-person international team** (China/India) delivering middleware operations for AIA Insurance across multiple Asia-Pacific sites; raised automation coverage from **10% to 50%**.
- Delivered multiple complex projects including data center migrations, site splits, and system builds; successfully migrated client systems from IBM WAS 6 to WAS 8.

---

## Certifications

**AWS Solutions Architect – Associate** (Nov 2022) · **CKA** (Aug 2021) · **RHCE** – Ansible 2.9 / RHEL 8 (Jun 2022) · **Azure Administrator Associate** (Apr 2022) · **Alibaba Cloud ACP** (Jul 2021) · **PMP** (Nov 2017) · **ITIL® Foundation** (Feb 2017) · **IBM WAS Network Deployment V8.0** (Aug 2014)

---

## Education

**Tianjin Polytechnic University** | B.Eng., Software Engineering | 2008 – 2012
