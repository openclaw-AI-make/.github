# OpenClaw AI Make 🦞

> OpenClaw 智能制造 - 智能备份、自动恢复、守护你的 AI 助手

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-Community-blue.svg)](https://docs.openclaw.ai)

---

## 🚀 快速开始

### 1. Guardian（推荐）

```bash
git clone https://github.com/openclaw-AI-make/openclaw-guardian.git
cd openclaw-guardian
cp notify.conf.example notify.conf
nano notify.conf  # 填入 Telegram Token
oc-config-backup    # 备份配置
oc-backup           # 完整备份
```

### 2. Disaster Recovery（可选）

```bash
git clone https://github.com/openclaw-AI-make/openclaw-disaster-recovery.git
cd openclaw-disaster-recovery
bash backup.sh daily
```

---

## 📦 核心技能

| 技能 | 说明 | 状态 |
|------|------|------|
| **[Guardian](openclaw-guardian/)** | 🛡️ 自动健康检查、配置回滚、服务恢复 | ✅ 推荐 |
| **[Disaster Recovery](openclaw-disaster-recovery/)** | 📦 NAS 备份、完整系统备份、灾难恢复 | ✅ 推荐 |
| **[Memory Isolation](openclaw-memory-isolation/)** | 🧠 15 类聚焦记忆、智能理解 | ✅ 推荐 |
| **[CLI](openclaw-cli/)** | 💻 OpenClaw 命令行工具 | ✅ 稳定 |
| **[Config](openclaw-config/)** | ⚙️ 配置管理技能 | ✅ 稳定 |

---

## 📚 文档中心

### 快速入门

| 文档 | 说明 |
|------|------|
| [quick-start.md](docs/quick-start.md) | 5 分钟快速部署指南 |
| [skills-index.md](docs/skills-index.md) | 完整技能索引 |
| [best-practices.md](docs/best-practices.md) | 最佳实践和技巧 |

### 核心参考

| 文档 | 说明 |
|------|------|
| [configuration.md](docs/configuration.md) | OpenClaw 完整配置参考 |
| [channels.md](docs/channels.md) | 渠道配置详解 |
| [tools-skills-hooks.md](docs/tools-skills-hooks.md) | 工具/技能/钩子使用 |
| [user-understanding.md](docs/user-understanding.md) | 用户习惯理解系统 |

---

## 🔒 隐私安全

**敏感信息处理**：
- Telegram Token → 占位符 + GitHub Secrets
- NAS 密码 → 占位符 + .private 目录
- 凭证文件 → .private/credentials/（不提交）

**配置 Secrets**：
```
Settings → Secrets and variables → Actions
添加：BOT_TOKEN, NAS_PASS, GITHUB_TOKEN
```

---

## 📊 仓库状态

| 仓库 | 说明 | 状态 |
|------|------|------|
| [openclaw-guardian](openclaw-guardian/) | 守护技能 | ✅ 活跃 |
| [openclaw-disaster-recovery](openclaw-disaster-recovery/) | 灾备系统 | ✅ 活跃 |
| [openclaw-memory-isolation](openclaw-memory-isolation/) | 记忆隔离 | ✅ 活跃 |
| [openclaw-cli](openclaw-cli/) | CLI 工具 | ✅ 稳定 |
| [openclaw-config](openclaw-config/) | 配置管理 | ✅ 稳定 |
| ~~openclaw-monitor~~ | 监控（已归档） | ⚠️ 归档 |
| ~~monitor-gateway~~ | 监控（已归档） | ⚠️ 归档 |
| ~~config-openclaw~~ | 配置（已归档） | ⚠️ 归档 |

---

## 🔗 相关资源

| 资源 | 链接 |
|------|------|
| OpenClaw 官方 | https://openclaw.ai |
| 官方文档 | https://docs.openclaw.ai |
| Discord 社区 | https://discord.gg/clawd |

---

## 📝 更新日志

### 2026-03-07 - 阶段 3 完成

- ✅ 同步 P1 技能（automation, workflow-automation, email-processor）
- ✅ 同步 P2 技能（pdf, xlsx, powerpoint-automation）
- ✅ 更新技能索引
- ✅ 技能同步率：64% (18/28)

### 2026-03-07 - 阶段 2 完成

- ✅ 创建统一文档（quick-start, skills-index, best-practices）
- ✅ 同步 P0 技能（screenshot, ssh-hardening, system_control）
- ✅ 更新组织主页
- ✅ 归档重复仓库（3 个）
- ✅ 文档中心：13 个核心文档

### 2026-03-07 - 精简优化

- ✅ 创建组织 openclaw-AI-make
- ✅ 部署 Guardian 守护系统
- ✅ 归档重复仓库（3 个）
- ✅ 同步核心技能（9 个）
- ✅ 创建文档中心（10 个文档）

---

<p align="center">
  <strong>🦞 OpenClaw AI Make - 智能制造，守护你的 AI 助手</strong>
</p>
