# EIS-2026: Industrial Sovereign Autonomy Standard
# EIS-2026: 工业主权自治标准

## Bilingual Governance Notice
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
