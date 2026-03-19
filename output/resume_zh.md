# 乔德立

**15522013699** | qiaodeli111@126.com | 深圳 | [github.com/qiaodeli111](https://github.com/qiaodeli111)

---

## 个人优势

14年DevOps/SRE经验，专注基础设施自动化与平台工程。主导构建了覆盖物理机（BMAAS）、私有云（CloudStack）及多云（AWS/阿里云/华为云/天翼云）的全栈IaC体系。具备Go/Python二次开发能力，自研多云Terraform Provider（[terraform-multicloud](https://github.com/qiaodeli111/terraform-multicloud)）及JetDev开发者工具箱。率先完成龙蜥Anolis OS ARM、UOS海光C86、OpenEuler等国产化平台全链路适配，支撑x86/ARM64/C86三架构标准化交付。持有 **AWS SAA、CKA、RHCE、Azure Admin、PMP** 认证。

---

## 核心技术栈

| 类别 | 技术 |
|------|------|
| **云平台** | CloudStack · AWS · 阿里云 · 华为云 · 天翼云 · Proxmox VE |
| **容器编排** | Kubernetes · Docker · Helm · Harbor · JFrog Artifactory |
| **IaC 自动化** | Terraform（自研Provider） · Ansible · Packer · Tinkerbell · cloud-init |
| **存储** | ZFS · DRBD · Linstor · LVM · Corosync/Pacemaker |
| **网络** | L4/L7 LB · BGP · VLAN · OVS/DPDK · PXE/iPXE · Redfish |
| **监控可观测** | Grafana · Prometheus · Loki · Fluentd · Zabbix |
| **安全合规** | Vault · Nessus · Lynis · Consul ACL · SSL/TLS · Trivy |
| **CI/CD** | GitLab CI · Jenkins · Goss · Ansible Tower |
| **操作系统** | Ubuntu · 龙蜥 Anolis OS · UOS · OpenEuler · Windows（x86/ARM64/C86） |
| **开发语言** | Go · Python · Shell/Bash · HCL |

---

## 工作经历

### 深圳捷誊技术有限公司 — DevOps Team Lead & 交付效能专家
**2024.10 – 至今 | 深圳**

同时管理 BMAAS、Terraform、镜像工厂、CloudStack、K8s、IT支撑、JetDev 共 **7个并行项目**，主导技术选型与架构设计，带领团队完成跨 **5+ 客户站点**的交付。

**平台化建设**

- **主导研发 JetDev 一站式DevOps工具箱**：集成 Ansible、Terraform、Packer、GitLab Runner 等核心工具，将 Ansible Role 项目脚手架生成时间缩短 **80%**，建立从代码审查到线上部署的标准化可追溯工作流，已在运维及测试团队推广落地。
- **自研多云统一 Terraform Provider（Go）**：兼容 AWS/阿里云/华为云/天翼云，基于 AWS 兼容 API 实现 CloudStack 资源编排，彻底消除多云配置碎片化，实现 IaaS 资源"一次编写、到处运行"。
- **构建 CloudStack 私有云平台**：基于 ZFS+Linstor 分布式存储（DRBD 9.3.0）和 VLAN 高级网络，完成 **13项**核心功能交付；ZFS 性能调优后 IOPS 从 **230k 提升至近 800k**（PCIe 5.0 32核），修复 DRBD 心跳参数实现 **7×24** 稳定运行；上线 Grafana 资源看板实时展示 CPU/内存/存储/公网IP分配率。

**自动化体系**

- **重构自动化镜像工厂（Packer）**：支持 Ubuntu/UOS/龙蜥Anolis OS/OpenEuler/Windows 共 **5类OS** × x86_64/ARM64/C86 **3架构**全矩阵打包；集成 Goss 自动化冒烟测试 + Lynis 安全审计；并发构建效率提升 **3.2倍**，流水线零失败连续运行超 **30天**，完成 **12项**镜像交付任务。
- **深度优化 BMAAS 裸金属自动装机平台**：新增磁盘自动选择、多网卡动态聚合（Bonding）、HookOS 可插拔驱动框架、Rescue 模式及离线装机流程；支持 x86/ARM64/C86 全架构，成功交付 **扬州电信** 新站点操作系统全流程部署；上线 redfish-batch-iso 工具实现批量 ISO 并发挂载。
- **设计并落地多套 GitLab CI/CD 流水线**：镜像工厂自动触发构建/上传/通知全链路；Ansible 项目"提交即测试"（动态拉起VM做部署和幂等性验证）；IaC 资源变更 MR 审批流，实现云资源申请自动化、可追溯。

**国产化适配与存储性能**

- **主导国产化平台全链路适配**：完成龙蜥 Anolis OS 8 ARM JetIce 镜像全流程打包（含 HA 组件 ZFS/DRBD/Corosync/Pacemaker 联调）；适配 UOS（海光C86）及 OpenEuler ZFS 模块编译验证；支撑多国产平台标准化交付。
- **主导存储性能工程**：设计并执行 fio 基准测试套件（随机读写/顺序读写/混合负载 **6类场景**，PCIe 3.0/5.0 对比），输出可归因性能报告；完成 ZFS thin-provisioning 性能评估与 Linstor 副本迁移策略验证。
- **完成 L4/L7 负载均衡性能测试**：执行完整测试用例，汇总数据并输出跨团队评审性能报告；完成 L4LB Docker 容器化迁移及 BGP 动态路由管理。

**客户交付与技术支撑**

- **主导多站点客户交付与现场问题排查**：空天院 JetIce 部署后网络丢包根因定位（网卡驱动/内核参数/DPDK/OVS）；厦门电信 **6项高危 CVE** 修复复测通过（含 CVE-2023-27350）；吉山数字生活 L4LB 容器化 + Consul ACL 安全基线全站达标；四川攀枝花巡检工具重新部署；无锡 Zabbix 告警全量接入凌霄平台。
- **主导公司内部网络整改**：全网 IP 盘点与归属映射、VLAN 划分、DNS/DHCP 策略部署、IPv4 地址池标准化，完成 **19项** IT 基础设施交付任务。
- **推进 K8s 集群平台化**：验证 Cluster API + CloudStack 方案可行性，确定"K8s on CloudStack + 外部LB + 共享存储"核心架构；规划 Velero + MinIO 备份与灾难演练；完成 JumpServer Helm Chart 迁移至 K8s + 正式版 SSL 证书升级。

---

### Kyndryl 深圳（由 IBM 拆分） — SRE 工程师（工具链方向）
**2021.09 – 2024.08 | 深圳**

### IBM 深圳 — SRE 工程师（工具链方向）
**2017.03 – 2021.09 | 深圳**

- 连续 **6年** 年度考核"超出预期"（Exceed Expectation），管理 **4–10人**跨文化团队（中国/印度）。
- 构建全面自动化运维体系：团队运维效率提升 **50%+**，运维质量提升 **90%+**，应用部署时间缩短 **80%**，变更请求处理时间减少 **50%+**。
- 管理 Chef/GitLab/Jenkins/Ansible Tower/UCD 全链路 DevOps 工具链，为业务 SRE 团队开发基础 Ansible/Chef 公共库。
- 作为 **AWS 架构咨询团队**成员，主导客户全球化架构改造：将 ECS 单体服务重设计为 EKS 集群化部署，引入 AWS Global Accelerator 分流加速，分离存储/数据库层，解决跨区访问延迟和成本问题。

---

### 天津恩恩科技有限公司 — 变更服务交付经理
**2016.05 – 2017.03**

- 利用 Excel + 自动化脚本重构变更管理流程，团队工作量减少 **80%**，月度报表自动化生成。

---

### DXC Technology — WebHosting 团队队长 / 运维工程师
**2012.06 – 2016.05**

- 带领 **4人国际团队**（中/印）为亚洲多地 AIA 友邦保险提供中间件运维服务，自动化程度从 **10% 提升至 50%**。
- 主导数据中心迁移、网站分割、新系统建立等多个复杂项目，成功迁移客户系统（IBM WAS6 → WAS8）。

---

## 认证证书

**AWS SAA**（2022.11） · **Azure Admin**（2022.04） · **阿里云ACP**（2021.07） · **CKA**（2021.08） · **RHCE**（Ansible 2.9/RHEL 8，2022.06） · **PMP**（2017.11） · **ITIL® Foundation**（2017.02） · **IBM WAS Network Deployment V8.0**（2014.08）

---

## 教育背景

**天津工业大学**（双一流） | 软件工程 本科 | 2008 – 2012
