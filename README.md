# EIS-2026: Industrial Sovereign Autonomy Standard
# EIS-2026: 工业主权自治标准

<!-- SEARCH_VISIBILITY_BEGIN -->
## Discoverability Snapshot / 检索曝光摘要

- Standard ID / 标准编号: `RR-ISAS`
- Repository / 仓库名: `ISAS-Core`
- A/B Recommended Variant / 推荐版本: `B`

### EN Summary / 英文摘要
Industrial sovereignty reference implementation, including identity, kinetics, and anchoring layers.

### CN Summary / 中文摘要
工业主权自治的参考实现，覆盖身份、动力学与锚定层。

### SEO Keywords / 检索关键词
`industrial-autonomy`, `did`, `ipfs`, `sovereignty`, `fdo`

### Suggested Search Phrases (EN)
- ISAS-Core RR-ISAS open standard
- ISAS-Core industrial-autonomy did github
- RR-ISAS industrial-autonomy reference implementation

### 建议检索短语（中文）
- ISAS-Core RR-ISAS 标准 规范
- ISAS-Core industrial-autonomy did 仓库
- RR-ISAS 参考实现 红岩 宪章

### A/B Hero Variants / 首屏 A/B 版本
- Variant A (Citation-First) / 引用优先: [`docs/readme-ab/README_HERO_A_CN_EN.md`](docs/readme-ab/README_HERO_A_CN_EN.md)
- Variant B (Adoption-First) / 落地优先: [`docs/readme-ab/README_HERO_B_CN_EN.md`](docs/readme-ab/README_HERO_B_CN_EN.md)
- Experiment Window / 观测窗口: 14 days

### Quick Links / 快速入口
- Governance Hub / 总入口: https://github.com/joy7758/RedRock-Constitution
- Standards Registry / 标准注册表: https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/STANDARDS_REGISTRY.md#rr-isas
- Repos Index / 仓库索引: https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/REPOS_INDEX_CN_EN.md
- Ecosystem Graph / 生态关系图: https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/ECOSYSTEM_GRAPH_CN_EN.md
- Onepager / 一页纸: https://github.com/joy7758/ISAS-Core/blob/main/docs/onepager/RR-ISAS_ONEPAGER_CN_EN.md
- Citation / 引用元数据: `CITATION.cff`
- Security Policy / 安全策略: `SECURITY.md`
- Machine-readable / 机器可读: `machine-readable/repository.json`
<!-- SEARCH_VISIBILITY_END -->

## Bilingual Governance Notice

## Standard Domain Entry / 标准域入口

- Standard ID / 标准编号：`RR-ISAS`
- Registry Row / 注册表定位：https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/STANDARDS_REGISTRY.md#rr-isas
- Hub / 总入口：https://github.com/joy7758/RedRock-Constitution
- Onepager / 一页纸：`docs/onepager/RR-ISAS_ONEPAGER_CN_EN.md`

**CN**: 所有标准文档均以中文与英文同步发布，英文为完整翻译版本。  
**EN**: All standards are published in Chinese and English, and the English content must be a full translation.

![System Demo](https://github.com/user-attachments/assets/a5e85f07-6f4f-494e-940e-d618deea9f76)

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](LICENSE)
[![Standard: FDO](https://img.shields.io/badge/Standard-FDO%202.0-orange.svg)](https://fairdo.org)
[![Status: Sovereign](https://img.shields.io/badge/Status-Sovereign-green.svg)]()

> **The eFDO Framework**: A reference implementation for Kinetic FAIR Digital Objects (K-FDO) with self-sovereign identity, decentralized anchoring, and state-based commercial licensing.
>
> **eFDO 框架**: 动力学 FAIR 数字对象 (K-FDO) 的参考实现，具有自我主权身份、去中心化锚定和基于状态的商业许可。

---

## 🏗 System Architecture / 系统架构

The EIS-2026 standard defines a closed-loop ecosystem for industrial assets. It ensures technical sovereignty through four distinct layers:
EIS-2026 标准定义了工业资产的闭环生态系统。它通过四个不同的层级确保技术主权：

### 1. Identity Layer / 身份层 (`did_generator.py`)
Implementation of **W3C Decentralized Identifiers (DID)**. It generates immutable `did:efdo:uuid` via `Ed25519` cryptographic keys, granting assets their own digital birthright.
**W3C 去中心化标识符 (DID)** 的实现。它通过 `Ed25519` 加密密钥生成不可变的 `did:efdo:uuid`，赋予资产自己的数字与生俱来的权利。

### 2. Kinetic Layer / 动力学层 (`robot_adapter.py`)
The "Physical-Digital" bridge. It injects real-time industrial telemetry (Torque, Temperature) and maintains a **Physical Circuit Breaker** to trigger halts during anomalies.
“物理-数字”桥梁。它注入实时工业遥测数据（扭矩、温度），并维护**物理断路器**以在异常期间触发停止。

### 3. Storage Layer / 存储层 (`ipfs_anchor.py`)
State snapshots are hashed and pinned to the **IPFS** network. This creates a content-addressable, tamper-proof audit trail for the asset's entire lifecycle.
状态快照被哈希并固定到 **IPFS** 网络。这为资产的整个生命周期创建了内容可寻址、防篡改的审计跟踪。

### 4. Commercial Layer / 商业层 (`license_vault.py`)
Dynamic enforcement of **GPL-3.0**. The system autonomously revokes the API `ACCESS_TOKEN` if the asset's health index falls below safety thresholds.
**GPL-3.0** 的动态执行。如果资产的健康指数低于安全阈值，系统会自动撤销 API `ACCESS_TOKEN`。

---

## 📐 Mathematical Model / 数学模型

The value and sovereign state of an eFDO asset are dynamically calculated using the following formula:
eFDO 资产的价值和主权状态使用以下公式动态计算：

$$V_{\mathrm{kinetic}} = V_{\mathrm{base}} \times (1 - \mathrm{Fatigue\_Index}) \times \alpha$$

**Where / 其中:**
* $\mathrm{Fatigue\_Index} = f(\mathrm{Torque}, \mathrm{Temp})$ / 疲劳指数
* **Alpha ($\alpha$):** Sovereign Coefficient (1.0 for valid license, 0.0 for revoked/halted). / 主权系数（1.0 表示许可证有效，0.0 表示已撤销/停止）。

---

## 🚀 Quick Start (STABLE DEPLOYMENT) / 快速开始（稳定部署）

Follow these steps to initialize the sovereign node.
按照以下步骤初始化主权节点。

```bash
# PHASE 01: TELEMETRY
# 执行实时遥测与监控服务：
python3 live_monitor.py

# PHASE 02: PUBLISH_CYCLE
# 执行 FDO 主权发布生命周期：
chmod +x publish.sh && ./publish.sh
```

**Logic Flow / 逻辑流程**: `EVOLVE -> INJECT_DATA -> ANCHOR_IPFS -> UPDATE_LICENSE`
**逻辑流程**: `进化 -> 注入数据 -> 锚定 IPFS -> 更新许可证`

---

## Node Metadata / 节点元数据

- **ARCHITECT**: Zhang Bin (FDO Specialist)
- **CONTACT**: joy7759@gmail.com
- **IDENTITY**: Mac-Mini-ZB (Sovereign Node 01)

---

## Belongs to RedRock Constitution / 隶属于红岩宪章体系

This repository is part of the RedRock Constitution architecture framework.

Please start from the central governance hub:

https://github.com/joy7758/RedRock-Constitution

本仓库属于红岩宪章体系，请从总入口开始阅读与理解：

https://github.com/joy7758/RedRock-Constitution

---

## Standard Domain / 标准域

This repository implements Standard Domain `RR-ISAS` under the RedRock Constitution framework.

本仓库实现红岩宪章标准域：`RR-ISAS`

Central Governance Hub:
https://github.com/joy7758/RedRock-Constitution

## Onepager / 一页纸

- `RR-ISAS` Onepager / 一页纸：`docs/onepager/RR-ISAS_ONEPAGER_CN_EN.md`
- Hub / 总入口：https://github.com/joy7758/RedRock-Constitution

<!-- ECOSYSTEM_LINKS_BEGIN -->
## Ecosystem Links / 生态关系链接

![quality-baseline](https://github.com/joy7758/ISAS-Core/actions/workflows/quality-baseline.yml/badge.svg)

### CN
- 总入口（宪章）：[RedRock-Constitution](https://github.com/joy7758/RedRock-Constitution)
- 标准注册表：[STANDARDS_REGISTRY](https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/STANDARDS_REGISTRY.md#rr-isas)
- 仓库总索引：[REPOS_INDEX_CN_EN](https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/REPOS_INDEX_CN_EN.md)
- 全局生态图：[ECOSYSTEM_GRAPH_CN_EN](https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/ECOSYSTEM_GRAPH_CN_EN.md)
- 机器可读元数据：[`machine-readable/repository.json`](machine-readable/repository.json)

### EN
- Governance hub: [RedRock-Constitution](https://github.com/joy7758/RedRock-Constitution)
- Standards registry: [STANDARDS_REGISTRY](https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/STANDARDS_REGISTRY.md#rr-isas)
- Repositories index: [REPOS_INDEX_CN_EN](https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/REPOS_INDEX_CN_EN.md)
- Global ecosystem graph: [ECOSYSTEM_GRAPH_CN_EN](https://github.com/joy7758/RedRock-Constitution/blob/main/docs/registry/ECOSYSTEM_GRAPH_CN_EN.md)
- Machine-readable metadata: [`machine-readable/repository.json`](machine-readable/repository.json)

### Related Repositories / 关联仓库
- [AASP-Core](https://github.com/joy7758/AASP-Core)
- [Kinetic-Robotics-FDO-Sovereignty](https://github.com/joy7758/Kinetic-Robotics-FDO-Sovereignty)
- [pFDO-Specification](https://github.com/joy7758/pFDO-Specification)
- [RedRock-Constitution](https://github.com/joy7758/RedRock-Constitution)

### Search Keywords / 检索关键词
`industrial-autonomy`, `did`, `ipfs`, `sovereignty`, `fdo`

### Bilingual Project Abstract / 双语项目摘要
- EN: Industrial sovereignty reference implementation, including identity, kinetics, and anchoring layers.
- CN: 工业主权自治的参考实现，覆盖身份、动力学与锚定层。
<!-- ECOSYSTEM_LINKS_END -->
