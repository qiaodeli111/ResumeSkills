# 技术栈与项目经验分析报告

> 来源：devops_report.md Sprint 进展报告（截至 2026-03-16）

---

## 1. 云平台与虚拟化

| 技术 | 应用场景 |
|------|----------|
| **CloudStack** | 私有云平台搭建与运维，物理机+虚拟机混合资源纳管，协同调度与故障隔离 |
| **Proxmox VE (PVE)** | 虚拟化集群管理，虚机迁移（跨集群导入导出） |
| **QEMU/KVM** | 虚拟机运行时（含 UEFI 固件、virtio-win 驱动注入、qcow2 镜像管理） |
| **libvirt** | VM 存活性探针与生命周期管理 |
| **华为云** | 多云资源管理（EIP 绑定、多网卡场景） |
| **AWS** | S3 生命周期策略自动化（热存转冰存）、CloudStack AWS 兼容 API 对接 |
| **多云管理 (cloudmux)** | 多云平台虚拟机资源监控与统一纳管 |

---

## 2. 容器与编排

| 技术 | 应用场景 |
|------|----------|
| **Kubernetes (K8s)** | 集群生命周期管理（scale-up/down, upgrade, backup/restore）、Cluster API + CloudStack 方案验证、Helm Chart 部署、Velero + MinIO 备份与灾难演练 |
| **Docker** | 容器化部署（L4LB Docker 化、Harbor 镜像仓库、Docker Compose 编排）、多平台镜像构建（buildx ARM64/x86_64） |
| **Harbor** | 企业级容器镜像仓库运维（数据库修复、双架构镜像同步） |
| **JFrog Artifactory** | 制品库管理（HA 架构设计：3节点+外部PG+OSS后端） |
| **Helm** | K8s 应用包管理与发布 |

---

## 3. 自动化与 IaC

| 技术 | 应用场景 |
|------|----------|
| **Ansible** | 自动化配置管理（Nessus 编排脚本、Consul ACL Role 升级、智能制造部署 Role、Vault/CloudVMScanner 部署） |
| **Terraform** | 自研 CloudStack Terraform Provider，通过 AWS 兼容 API 实现资源编排；华为云多网卡 EIP 绑定优化 |
| **Packer** | 镜像工厂（多 OS、多架构镜像自动化打包，Goss 集成冒烟测试，Lynis 安全加固预装） |
| **cloud-init** | 虚机初始化（主机名配置、MTU 设置、网络参数注入） |
| **Tinkerbell** | 裸金属装机引擎（workflow 执行、Rescue ISO 集成） |
| **osdef** | 声明式配置管理（provision_steps 配置即代码，GitOps 管理） |

---

## 4. 存储技术

| 技术 | 应用场景 |
|------|----------|
| **ZFS** | 存储池管理（zfs / zfs_thin 模式）、fio 性能基准测试（PCIe 3.0/5.0）、thin-provisioning 切换方案调研 |
| **DRBD** | 分布式复制块设备（DRBD 9.3.0 + drbd-utils 9.33.0），心跳参数调优（ping-timeout/ping-int），双活存储部署 |
| **Linstor** | 与 CloudStack 耦合的存储编排，副本迁移策略（双/单副本） |
| **LVM** | 逻辑卷管理（LVM 版 Ubuntu 镜像打包、cloud-init 与 lvm2 初始化时序修复） |
| **Corosync/Pacemaker** | 高可用集群组件（HA 联调验证） |

---

## 5. 网络技术

| 技术 | 应用场景 |
|------|----------|
| **L4/L7 负载均衡** | 性能测试、Docker 化部署、BGP 动态路由管理、VIP 绑定 |
| **BGP** | 虚拟交换机拉通，L4LB 路由表动态管理 |
| **VLAN** | 网络域自动化开局、子网配置、ACL 规则管理 |
| **OVS / DPDK** | 网络丢包排查（内核参数、网卡驱动、DPDK 配置） |
| **DNS / DHCP** | 公司内部网络整改，策略部署与 rollout |
| **PXE / iPXE** | 网络启动装机（TFTP 配置、autoexec.ipxe） |
| **MTU 9000 (Jumbo Frame)** | 多网卡环境 MTU 配置与验证 |
| **Redfish** | 服务器远程管理（批量 ISO 挂载工具） |

---

## 6. CI/CD 与 DevOps 工具

| 技术 | 应用场景 |
|------|----------|
| **GitLab CI/CD** | 流水线设计与实施（自动打包、自动上传、自动通知）、ARM Runner 管理、多平台构建 |
| **Goss** | 镜像打包过程中的自动化冒烟测试（journal、内核版本、必备软件校验） |
| **JFrog Artifactory** | 制品库（镜像上传、语义化版本归档） |
| **Consul** | 服务发现与配置管理（ACL 策略、Token 分级授权） |
| **Vault** | 密钥管理服务部署与运维 |
| **JumpServer** | 堡垒机（K8s 迁移 + SSL 证书升级） |
| **iTop** | IPAM、IP Discovery、Datacenter View 资产管理 |
| **Discourse** | 研发协作论坛（LDAP SSO 集成、权限矩阵管理） |

---

## 7. 监控与日志

| 技术 | 应用场景 |
|------|----------|
| **Grafana** | 资源看板（CloudStack API 数据源）、LDAP 集成统一认证、CPU/内存/存储/公网IP 分配率实时展示 |
| **Prometheus** | 监控集成（K8s 部署验证路径） |
| **Loki** | 集中日志采集后端 |
| **Fluentd / FluentBit** | 日志采集（VM 集中日志 → Loki）、JetMon 统一配置 |
| **Zabbix** | 告警接入（全量接入凌霄平台、短信转发） |
| **fio** | 存储性能基准测试工具（随机读/写、顺序读/写、混合负载 6 类场景） |

---

## 8. 安全与合规

| 技术 | 应用场景 |
|------|----------|
| **Nessus** | 漏洞扫描（标准化部署、License 管理、离线插件加载） |
| **Lynis** | 安全审计工具（预装至 OS 镜像、基础加固策略集成） |
| **Trivy** | 容器镜像漏洞扫描（流水线集成规划） |
| **OpenVAS** | 漏洞扫描工具对比评估 |
| **SSL/TLS 证书** | CA 机构正式证书申请、Let's Encrypt + Nginx Ingress HTTPS |
| **Consul ACL** | 服务级访问控制（策略模型设计、Token 分级授权） |
| **CVE 漏洞修复** | 高危漏洞整改与复测（如 CVE-2023-27350） |
| **Tuned** | 系统性能调优 Profile（NUMA-CPU 绑定、MTU 参数） |

---

## 9. 操作系统

| 操作系统 | 应用场景 |
|----------|----------|
| **Ubuntu 22.04 / 24.04** | 主力基础镜像（LVM 版本打包、Python 3.13 统一） |
| **龙蜥 Anolis OS 8** | ARM 架构国产化适配（JetIce 镜像全流程打包与验证） |
| **UOS (统信)** | 海光 C86 平台适配、L4/L7 网络服务适配 |
| **OpenEuler (欧拉)** | ZFS 编译与模块加载测试、LVM 初始化兼容性验证 |
| **Windows 11** | qcow2 镜像标准化部署（UEFI + virtio-win 驱动注入） |

---

## 10. 编程语言与开发

| 语言/工具 | 应用场景 |
|-----------|----------|
| **Go** | Terraform Provider 自研、基础设施工具开发 |
| **Python 3.13** | 运维工具链（uv + pyenv 多版本管理）、全栈镜像统一运行时 |
| **Shell/Bash** | Provision 脚本、自动化运维脚本、装机流程脚本 |
| **HCL (Terraform)** | 基础设施即代码配置 |
| **YAML** | Ansible Playbook、Helm Chart、CI/CD 流水线定义 |

---

## 11. 项目管理

| 实践 | 说明 |
|------|------|
| **敏捷 Sprint 管理** | 每周 Sprint 迭代（W11/W12/W13），每日站会跟踪机制 |
| **多项目并行管理** | 同时管理 BMAAS、Terraform、YATC、CloudStack、Packer、IT支持、JetDev 共 7 个项目 |
| **跨团队协作** | 联合评审（Platform Infra 团队）、客户交付协同（空天院、扬州电信、厦门电信、吉山数字生活、四川攀枝花） |
| **优先级驱动** | 任务按极高/高/一般/低四级优先级分层管理 |

---

## 关键项目成就（量化数据）

### BMAAS 物理机自动装机平台
- 完成 **12+ 项** 核心功能交付，覆盖 PXE 装机、Redfish 批量 ISO 挂载、HookOS 定制、Rescue 模式等全链路
- 支持 **x86_64 + ARM64** 双架构裸金属装机
- 支持 **国产化平台**（海光 C86）适配
- 上线 **redfish-batch-iso** 工具，实现并发挂载 + 自动化配置生成
- 成功交付 **扬州电信** 新站点操作系统全流程部署

### 镜像工厂（Packer）
- 完成 **12 项** 镜像打包任务交付
- 流水线支持多任务并行构建，构建效率提升约 **3.2 倍**
- 流水线 **零失败运行超 30 天**
- 覆盖 **5+ 操作系统**（Ubuntu、UOS、龙蜥 Anolis OS、OpenEuler、Windows 11）
- 覆盖 **双架构**（x86_64 / ARM64）镜像打包
- 集成 **Goss 自动化冒烟测试** + **Lynis 安全审计**

### 多云 Terraform Provider 自研
- 自研 CloudStack Terraform Provider，通过 **AWS 兼容 API** 实现资源编排
- 支持华为云多网卡 EIP 绑定优化

### CloudStack 私有云搭建与运维
- 完成 **13 项** 已完成任务，覆盖网络、存储、安全、监控全栈
- 实现 **物理机 + 虚拟机混合资源纳管**
- 上线 **Grafana 资源看板**，实时展示 CPU/内存/存储/公网 IP 分配率
- DRBD 稳定性修复后实现 **7x24 小时** 稳定运行
- ZFS 性能测试：32 核调优后 IOPS 从 230k 提升至接近 **800k**（PCIe 5.0）

### K8s 集群管理
- 验证 **Cluster API + CloudStack** 方案可行性
- 确定 **"K8s on CloudStack + 外部 LB + 共享存储"** 核心架构
- 规划 **Velero + MinIO** 备份与灾难演练方案
- JumpServer 向 K8s 迁移（Helm Chart + SSL 证书升级）

### JetDev 工具箱
- 完成 **4 项** 核心功能交付（OS 镜像上传、版本管理、参数记忆、双架构镜像同步）
- 集成 CloudStack Terraform Provider 规划中
- 打通标准化双架构镜像同步流程（docker.io / k8s.io → 内部 Harbor）

### 客户交付项目
| 客户 | 交付内容 |
|------|----------|
| **扬州电信** | 全流程操作系统部署 + 遗留问题闭环 |
| **厦门电信** | 安全漏洞扫描修复（6 项高危 CVE 已修复并复测通过） |
| **吉山数字生活** | L4LB 容器化迁移 + 全站 Consul ACL 安全基线达标 |
| **空天院** | JetIce 安装后网络丢包问题排查（进行中） |
| **四川攀枝花** | 巡检工具整理与重新部署 |
| **无锡** | Zabbix 告警全量接入凌霄平台 + 短信转发 |
| **智能制造项目** | 自动化部署 Ansible Role 交付 |

### IT 基础设施建设
- 完成 **19 项** IT 支持任务交付
- 上线多云 VM 资源利用率看板，闲置超 **72 小时** 自动告警
- 运维 Docker 镜像集成 **23 个** 常用工具（jq/yq/helm/kubectl/awscli/tfenv 等）
- Discourse 论坛上线 + LDAP SSO + 权限矩阵管理
