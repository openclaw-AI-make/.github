# OpenClaw AI Make 🦞

> OpenClaw 智能制造 - 智能备份、自动恢复、守护你的 AI 助手

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-Community-blue.svg)](https://docs.openclaw.ai)

---

## 📦 项目列表

### 核心项目

| 项目 | 说明 | 状态 | Stars |
|------|------|------|-------|
| **[openclaw-guardian](openclaw-guardian)** | 🛡️ 守护技能 - 自动健康检查、配置回滚、服务恢复 | ✅ 最新 | ⭐ |
| **[openclaw-disaster-recovery](openclaw-disaster-recovery)** | 📦 灾备系统 v2.0 - 完整备份和一键恢复 | ✅ 稳定 | ⭐ |
| **[openclaw-memory-isolation](openclaw-memory-isolation)** | 🧠 记忆隔离 - 会话历史独立存储 | ✅ 稳定 | ⭐ |
| **[openclaw-monitor](openclaw-monitor)** | 📊 监控技能 - Gateway 状态监控和告警 | ✅ 稳定 | ⭐ |

### 工具项目

| 项目 | 说明 | 状态 | Stars |
|------|------|------|-------|
| **[openclaw](openclaw)** | ⚙️ OpenClaw 配置文件 | ⚠️ 待整理 | ⭐ |
| **[config-openclaw](config-openclaw)** | ⚙️ OpenClaw 配置备份 | ⚠️ 待整理 | ⭐ |
| **[monitor-gateway](monitor-gateway)** | 🔍 监控网关 | ⚠️ 待整合 | ⭐ |
| **[notify-gateway](notify-gateway)** | 📢 通知网关 | ⚠️ 待整合 | ⭐ |
| **[ai-assistant-tools](ai-assistant-tools)** | 🤖 AI 助手工具集 | ⚠️ 待整理 | ⭐ |

---

## 🚀 快速开始

### 安装 Guardian

```bash
# 克隆仓库
git clone https://github.com/openclaw-AI-make/openclaw-guardian.git
cd openclaw-guardian

# 配置
cp notify.conf.example notify.conf
cp nas.conf.example nas.conf
nano notify.conf
nano nas.conf

# 使用
oc-config-backup    # 备份配置
oc-backup           # 完整备份
oc-status           # 查看状态
```

### 安装灾备系统

```bash
git clone https://github.com/openclaw-AI-make/openclaw-disaster-recovery.git
cd openclaw-disaster-recovery
```

---

## 📊 系统架构

```
┌─────────────────────────────────────────────────────────┐
│                   OpenClaw Guardian                      │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐     │
│  │ 健康检查    │  │ 配置备份    │  │ 服务恢复    │     │
│  │ (每分钟)    │  │ (5 分钟回滚) │  │ (自动重启)  │     │
│  └─────────────┘  └─────────────┘  └─────────────┘     │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│              OpenClaw Disaster Recovery                  │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐     │
│  │ NAS 备份     │  │ 本地备份    │  │ 恢复测试    │     │
│  │ (每天 3AM)   │  │ (变化时)    │  │ (每月 1 日)   │     │
│  └─────────────┘  └─────────────┘  └─────────────┘     │
└─────────────────────────────────────────────────────────┘
```

---

## 🔒 安全说明

**敏感信息处理**：

| 信息 | 处理方式 |
|------|---------|
| Telegram Token | 使用占位符 + GitHub Secrets |
| NAS 密码 | 使用占位符 + GitHub Secrets |
| 凭证文件 | 加入 .gitignore，不提交 |
| 日志文件 | 加入 .gitignore，不提交 |

**配置 Secrets**：

在 GitHub 仓库设置中添加：
```
Settings → Secrets and variables → Actions

添加：
- BOT_TOKEN
- NAS_PASS
- GITHUB_TOKEN
```

---

## 📝 变更日志

### 2026-03-07

- ✅ 创建组织 `openclaw-AI-make`
- ✅ 转移 8 个 OpenClaw 仓库
- ✅ 创建 `openclaw-guardian` 仓库
- ✅ 发布 Guardian v1.0.0

---

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

---

## 📄 许可

MIT License - 详见各仓库 LICENSE 文件

---

## 🔗 相关链接

| 链接 | 说明 |
|------|------|
| [OpenClaw 官方](https://openclaw.ai) | OpenClaw 官网 |
| [文档](https://docs.openclaw.ai) | OpenClaw 文档 |
| [Discord](https://discord.gg/clawd) | 社区 Discord |
| [ClaWHub](https://clawhub.com) | 技能市场 |

---

<p align="center">
  <strong>🦞 OpenClaw AI Make - 智能制造，守护你的 AI 助手</strong>
</p>
