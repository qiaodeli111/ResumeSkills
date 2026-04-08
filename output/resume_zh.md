# 乔德立

**15522013699** | qiaodeli111@126.com | 深圳 | [github.com/qiaodeli111](https://github.com/qiaodeli111)

---

## 个人优势

14年DevOps/SRE经验，专注私有云平台工程与基础设施自动化。主导从0到1构建并持续演进覆盖物理机（BMAAS）、私有云（CloudStack）及多云（AWS/阿里云/华为云/天翼云）的全栈IaC体系。具备Go/Python二次开发能力，自研多云Terraform Provider（[terraform-multicloud](https://github.com/qiaodeli111/terraform-multicloud)）及JetDev开发者工具箱。率先完成龙蜥Anolis OS ARM、UOS海光C86、OpenEuler等国产化平台全链路适配，支撑x86/ARM64/C86三架构标准化交付。持有 **AWS SAA、CKA、RHCE、Azure Admin、PMP** 认证。

---

## 核心技术栈

| 类别 | 技术 |
|------|------|
| **云平台** | CloudStack · AWS · 阿里云 · 华为云 · 天翼云 · Proxmox VE |
| **容器编排** | Kubernetes · Docker · Helm · Harbor · JFrog Artifactory |
| **IaC 自动化** | Terraform（自研Provider） · Ansible · Packer · Tinkerbell · cloud-init |
| **存储** | ZFS · DRBD · Linstor · LVM · Corosync/Pacemaker |
| **网络** | L4/L7 LB · BGP · VLAN · OVS/DPDK · PXE/iPXE · Redfish |
| **监控可观测** | Grafana · Prometheus · Alertmanager · Loki · Fluentd · Zabbix |
| **安全合规** | Vault · Nessus · Lynis · Consul ACL · SSL/TLS · Trivy |
| **CI/CD & GitOps** | GitLab CI · ArgoCD · Helm · Goss · Jenkins · Ansible Tower |
| **操作系统** | Ubuntu · 龙蜥 Anolis OS · UOS · OpenEuler · Windows（x86/ARM64/C86） |
| **开发语言** | Go · Python · Shell/Bash · HCL |

---

## 工作经历

### 深圳捷誊技术有限公司 — DevOps Team Lead & 交付效能专家
**2024.10 – 至今 | 深圳**

同时统筹 BMAAS、Terraform、镜像工厂、CloudStack、K8s、IT支撑、JetDev 共 **7个并行项目**，主导技术选型与架构设计，带领团队完成跨 **5+ 客户站点**的交付。

#### Kubernetes 平台建设与 GitOps 规范落地

- **主导 K8s on CloudStack 从0到1落地**：确立"K8s 控制面托管于 CloudStack VM + 应用工作负载运行于 K8s"混合云架构，完成控制面高可用设计（etcd HA + kubelet 安全加固）、CNI 选型（Calico over CloudStack SR-IOV）及 CSI 与私有云存储池深度集成，验证 Cluster API + CloudStack Provider 实现动态扩缩容的可行性。
- **基于 ArgoCD 制定并推行自动化部署规范**：构建以 ArgoCD 为核心的 GitOps 工作流，规范 Git 仓库结构（App仓库与Config仓库分离）、Helm Chart 版本管理策略及环境晋级流程（dev → staging → prod）；制定团队统一的 Application/AppProject 权限模型与同步策略（自动同步 + 手动审批双模式），将部署流程从"人工 kubectl apply"迁移为"Git PR 即部署"，显著提升变更可追溯性与回滚效率。
- **核心服务 K8s 迁移**：完成 JumpServer Helm Chart 迁移至 K8s 并集成 Cert-Manager 正式版 SSL 证书；完成 JFrog Artifactory K8s 高可用架构设计（PostgreSQL HA + S3存储后端 + Nginx 反向代理）并进入 POC 与吞吐压测阶段；规划 Velero + MinIO 备份体系与灾备演练方案（含 RPO/RTO 指标设计与故障注入剧本）。

#### CloudStack 私有云平台建设与运维

- **主导平台从0到1落地**：基于 ZFS+LINSTOR（DRBD 9.3.0）和 VLAN 高级网络完成私有云初始化部署，完成混合资源纳管（物理机+虚拟机统一管理面）、多架构支持等 **12项**核心功能交付；ZFS 性能调优后 IOPS 从 **230k 提升至近 800k**（PCIe 5.0）；修复 DRBD 心跳参数实现 **7×24** 稳定运行。
- **深度排查平台疑难故障**：定位 VM 创建失败（Secondary Storage 挂载异常）、VM 迁移中断（VR 资源竞争）及 VM 自动进入只读模式（host kernel 5.10 下 xfs_repair 异常触发只读挂载）等多类疑难问题，独立完成根因分析、patch 提交与临时规避 SOP 输出。
- **可观测性建设**：关键指标（vm.state、host.status、storage.capacity.used）接入 Prometheus + Alertmanager，告警响应时效由**小时级缩短至分钟级**；上线 Grafana 资源看板，实时展示 CPU/内存/存储分配率及 Top 使用者。
- **自研 Terraform Provider（Go）实现 CloudStack IaC**：基于 AWS 兼容 API 实现 CloudStack 资源声明式编排，同步兼容 AWS/阿里云/华为云/天翼云，彻底消除多云配置碎片化。

#### 裸金属自动化装机平台（BMAAS）

- **扩展 Tinkerbell/HookOS 平台能力**：新增 HookOS 可插拔驱动模块框架，构建 Rescue 模式（集成 tink CLI + workflow 执行引擎）作为完整降级方案；上线 redfish-batch-iso 工具实现多服务器并发批量 ISO 挂载 + 自动配置生成；将 BMAAS 后端迁移至 CloudStack，完成资源纳管与 workflow 触发稳定对接。
- **提升无人值守装机可靠性**：通过 cloud-init 实现主机名自动转大写、MTU 9000 多网卡默认配置、磁盘自动选择策略（容量/型号/接口类型）；支持 x86/ARM64/C86 全架构，成功交付电信运营商新站点操作系统全流程端到端部署。

#### 操作系统镜像工厂（Packer）

- **构建多OS多架构镜像自动化流水线**：支持 Ubuntu / UOS / 龙蜥 Anolis OS / OpenEuler / Windows 共 **5类OS** × x86_64/ARM64/C86 **3架构**全矩阵打包；集成 Goss 自动化冒烟测试 + Lynis 安全审计 + Trivy 漏洞扫描；并发构建效率提升 **3.2倍**，流水线零失败连续运行超 **30天**，完成 **13项**镜像交付任务。
- **国产化平台镜像适配**：完成龙蜥 Anolis OS 8 ARM 全流程打包（含 ZFS/DRBD/Corosync/Pacemaker HA 组件联调，内核升级至 6.6.102）；适配 UOS 海光C86 硬件平台内核驱动与固件；统一镜像内 Python 版本至 3.13（uv 管理 + 自动激活），支撑研发与运维共用底座。

#### 运维效率工具链（JetDev）& IT 基础设施

- **主导研发 JetDev 一站式 DevOps 工具箱**：集成 Ansible、Terraform、Packer、GitLab Runner 等核心工具，Ansible Role 脚手架生成时间缩短 **80%**；支持多版本镜像缓存、升级感知与配置继承，已在运维及测试团队推广落地。
- **IT 基础设施建设**：主导全网 IP 盘点与 VLAN 重规划，完成多楼层机柜标准化改造，IPAM 与 DNS/DHCP 双向同步；开发 Shell 脚本批量采集服务器硬件资产数据，首轮 20 台生产服务器采集**准确率 98.7%**，对接 ITOP API 实现资产自动导入；完成 **19项** IT 基础设施交付任务。
- **客户项目交付支撑**：为政企、运营商等多类客户提供 OS 镜像定制适配（含信创异构硬件）、L4/L7 LB 性能测试与压测报告输出、高危 CVE 修复复测（含 CVE-2023-27350）及安全基线（Consul ACL + 等保合规）落地。

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

- 带领 **4人国际团队**（中/印）为亚洲多地客户提供中间件运维服务，自动化程度从 **10% 提升至 50%**。
- 主导数据中心迁移、网站分割、新系统建立等多个复杂项目，成功迁移客户系统（IBM WAS6 → WAS8）。

---

## 认证证书

**AWS SAA**（2022.11） · **Azure Admin**（2022.04） · **阿里云ACP**（2021.07） · **CKA**（2021.08） · **RHCE**（Ansible 2.9/RHEL 8，2022.06） · **PMP**（2017.11） · **ITIL® Foundation**（2017.02） · **IBM WAS Network Deployment V8.0**（2014.08）

---

## 教育背景

**天津工业大学**（双一流） | 软件工程 本科 | 2008 – 2012
