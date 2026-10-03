<p align="center">
  <img alt="TinyClaw-Labs Logo" src="./assets/logo-512.png" width="220">
</p>

# TinyClaw-Labs

[![Rust](https://img.shields.io/badge/rust-2021-orange?logo=rust)](https://www.rust-lang.org)
[![Java](https://img.shields.io/badge/java-17+-blue?logo=openjdk)](https://openjdk.org)
[![Python](https://img.shields.io/badge/python-3.10+-yellow?logo=python)](https://python.org)
[![ESP32](https://img.shields.io/badge/ESP32-supported-green?logo=espressif)](https://www.espressif.com)
[![License](https://img.shields.io/badge/License-Apache_2.0-green?style=flat-square)](LICENSE)

**章鱼架构 AI 智能体执行引擎 — 从云端到边缘的全栈 Agent 基础设施**

> 零信任 · 流式执行 · 亚秒响应 · 企业安全 · MCP 原生

---

## 关于我们

TinyClaw-Labs 专注于 **AI 智能体执行引擎** 的研发，提供从云端到边缘的全栈 Agent 基础设施。核心设计理念是**章鱼架构** — 每个触手（Agent）独立运作，共享中枢神经系统（记忆/状态/通信）。

### 核心特性

- **零信任安全** — 企业级安全模型，端到端加密
- **流式执行** — Talk-while-executing，亚秒级响应
- **MCP 原生** — 原生支持 Model Context Protocol
- **多语言实现** — Rust / Java / Python，设计理论完全一致
- **边缘计算** — 支持 ESP32、树莓派、Jetson Nano 等边缘设备

---

## 项目矩阵

### 核心引擎

| 项目 | 语言 | 说明 |
|------|------|------|
| [tinyclaw](https://github.com/tinyclaw-labs/tinyclaw) | Rust | 核心引擎 — 零信任流式 AI 执行引擎 |
| [tinyclaw-4j](https://github.com/tinyclaw-labs/tinyclaw-4j) | Java | Java 实现 — 100% 兼容 OpenClaw 配置 |
| [tinyclaw-pi](https://github.com/tinyclaw-labs/tinyclaw-pi) | Python | 轻量全栈版 — 专为树莓派/NAS/边缘节点设计 |

### 边缘与硬件

| 项目 | 语言 | 说明 |
|------|------|------|
| [tinyclaw-esp32](https://github.com/tinyclaw-labs/tinyclaw-esp32) | C++ | ESP32 MCP 聊天机器人 |
| [tinyclaw-edge](https://github.com/tinyclaw-labs/tinyclaw-edge) | Rust | 边缘运行时 — 树莓派/Jetson Nano |

### 通信与集群

| 项目 | 语言 | 说明 |
|------|------|------|
| [tinyclaw-nats](https://github.com/tinyclaw-labs/tinyclaw-nats) | Rust | 集群通信中枢 — NATS 原生 Leaf Node 架构 |

### 插件生态

| 项目 | 语言 | 说明 |
|------|------|------|
| [tinyclaw-plugins](https://github.com/tinyclaw-labs/tinyclaw-plugins) | TypeScript | TinyClaw 插件集合 |
| [tinyclaw-pi-plugins](https://github.com/tinyclaw-labs/tinyclaw-pi-plugins) | Python | TinyClaw-Pi 插件集合 |
| [tinyclaw-4j-plugins](https://github.com/tinyclaw-labs/tinyclaw-4j-plugins) | Java | TinyClaw-4j 插件集合 |

### Android 自动化

| 项目 | 语言 | 说明 |
|------|------|------|
| [claw-adb-swarm](https://github.com/tinyclaw-labs/claw-adb-swarm) | Rust | Android 设备群控引擎 — ADB/UI/Macro + MCP/REST/CLI |
| [claw-android-bridge](https://github.com/tinyclaw-labs/claw-android-bridge) | Kotlin | Android 自动化键盘 — UI 自动化/截图/手势/事件流 |
| [claw-scrcpy-swarm](https://github.com/tinyclaw-labs/claw-scrcpy-swarm) | Rust | scrcpy 设备群控 |

---

## 架构概览

```
┌─────────────────────────────────────────────────────────────┐
│                    云端 (Cloud)                              │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐         │
│  │  TinyClaw   │  │ TinyClaw-4j │  │ TinyClaw-Pi │         │
│  │   (Rust)    │  │   (Java)    │  │  (Python)   │         │
│  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘         │
│         └────────────────┼────────────────┘                 │
│                          │                                  │
│              ┌───────────▼───────────┐                     │
│              │   TinyClaw-NATS       │                     │
│              │   集群通信中枢         │                     │
│              └───────────┬───────────┘                     │
└──────────────────────────┼──────────────────────────────────┘
                           │
┌──────────────────────────┼──────────────────────────────────┐
│                    边缘 (Edge)                               │
│  ┌──────────────┐  ┌──────▼──────┐  ┌──────────────┐       │
│  │  ESP32       │  │  树莓派     │  │  Jetson Nano │       │
│  │  TinyClaw   │  │  TinyClaw  │  │  TinyClaw   │       │
│  │  -ESP32     │  │  -Edge     │  │  -Edge      │       │
│  └──────────────┘  └─────────────┘  └──────────────┘       │
└─────────────────────────────────────────────────────────────┘
```

---

## 技术栈

| 层级 | 技术 |
|------|------|
| **核心引擎** | Rust (tokio) · Java (Spring Boot) · Python (asyncio) |
| **通信** | NATS · WebSocket · MCP Protocol · REST API |
| **AI 集成** | OpenClaw · LLMs · Agent Skills · Function Calling |
| **边缘** | ESP-IDF · Raspberry Pi OS · JetPack |
| **Android** | ADB · scrcpy · UI Automator · Accessibility |

---

## 快速开始

### TinyClaw (Rust)

```bash
git clone https://github.com/tinyclaw-labs/tinyclaw.git
cd tinyclaw
cargo build --release
```

### TinyClaw-4j (Java)

```bash
git clone https://github.com/tinyclaw-labs/tinyclaw-4j.git
cd tinyclaw-4j
mvn clean package
```

### TinyClaw-Pi (Python)

```bash
git clone https://github.com/tinyclaw-labs/tinyclaw-pi.git
cd tinyclaw-pi
pip install -r requirements.txt
python main.py
```

### ESP32

```bash
git clone https://github.com/tinyclaw-labs/tinyclaw-esp32.git
cd tinyclaw-esp32
# Follow ESP-IDF setup guide
idf.py build
```

---

## 相关生态

| 项目 | 说明 |
|------|------|
| [PartMe AI](https://github.com/partme-ai) | AI 智能体生态组织 |
| [OpenClaw](https://github.com/partme-ai/openclaw) | AI Agent 网关 |
| [Full Stack Skills](https://github.com/partme-ai/full-stack-skills) | 454 个 Agent Skills |

---

## 贡献指南

欢迎贡献！每个子项目都有独立的贡献指南。

1. **Fork** 目标仓库
2. 创建特性分支
3. 提交 PR

---

## 联系我们

- Email: [partmeai@gmail.com](mailto:partmeai@gmail.com)
- GitHub: [github.com/tinyclaw-labs](https://github.com/tinyclaw-labs)

---

<div align="center">

**章鱼架构 · 从云端到边缘的全栈 Agent 基础设施**

Made with ❤️ by TinyClaw-Labs

</div>
