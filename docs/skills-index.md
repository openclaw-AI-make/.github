# OpenClaw 技能索引

> 完整技能列表和说明

---

## 📊 技能分类

### 核心技能（推荐）⭐⭐⭐⭐⭐

| 技能 | 说明 | 状态 | 安装 |
|------|------|------|------|
| **[Guardian](#guardian)** | 🛡️ 自动健康检查、配置回滚、服务恢复 | ✅ 推荐 | `git clone` |
| **[Disaster Recovery](#disaster-recovery)** | 📦 NAS 备份、完整系统备份、灾难恢复 | ✅ 推荐 | `git clone` |
| **[Memory Isolation](#memory-isolation)** | 🧠 15 类聚焦记忆、智能理解、上下文优化 | ✅ 推荐 | `git clone` |

---

### 系统技能 ⭐⭐⭐⭐

| 技能 | 说明 | 状态 | 安装 |
|------|------|------|------|
| **[CLI](#cli)** | 💻 OpenClaw 命令行工具 | ✅ 稳定 | `git clone` |
| **[Config](#config)** | ⚙️ 配置管理技能 | ✅ 稳定 | `git clone` |
| **[System Control](#system-control)** | 🎛️ 系统控制（ctl） | ✅ 稳定 | 已内置 |
| **[Systemd](#systemd)** | ⚙️ systemd 服务管理 | ✅ 稳定 | 已安装 |

---

### 安全技能 ⭐⭐⭐⭐

| 技能 | 说明 | 状态 | 安装 |
|------|------|------|------|
| **[SSH Hardening](#ssh-hardening)** | 🔐 SSH 安全加固 | ✅ 稳定 | 已安装 |
| **[Clawsec](#clawsec)** | 🔒 安全工具集 | ✅ 稳定 | 已安装 |

---

### 办公技能 ⭐⭐⭐

| 技能 | 说明 | 状态 | 安装 |
|------|------|------|------|
| **[PDF](#pdf)** | 📄 PDF 处理 | ✅ 稳定 | 已安装 |
| **[Excel](#xlsx)** | 📊 Excel 处理 | ✅ 稳定 | 已安装 |
| **[PPT](#powerpoint-automation)** | 📊 PPT 自动化 | ✅ 稳定 | 已安装 |

---

### 开发技能 ⭐⭐⭐

| 技能 | 说明 | 状态 | 安装 |
|------|------|------|------|
| **[Linux Server Expert](#linux-server-expert)** | 🐧 Linux 服务器专家 | ✅ 稳定 | 已安装 |
| **[Mobile Developer](#mobile-developer)** | 📱 移动开发 | ✅ 稳定 | 已安装 |
| **[HarmonyOS Dev](#harmonyos-dev)** | 📱 鸿蒙开发 | ✅ 稳定 | 已安装 |
| **[Nginx Optimizer](#nginx-config-optimizer)** | ⚙️ Nginx 配置优化 | ✅ 稳定 | 已安装 |

---

### 自动化技能 ⭐⭐⭐

| 技能 | 说明 | 状态 | 安装 |
|------|------|------|------|
| **[Automation](#automation)** | 🤖 任务自动化 | ✅ 稳定 | 已安装 |
| **[Workflow Automation](#workflow-automation)** | 📊 工作流自动化 | ✅ 稳定 | 已安装 |
| **[Email Processor](#email-processor)** | 📧 邮件处理 | ✅ 稳定 | 已安装 |
| **[Web Scraper](#web-scraper)** | 🕸️ 网页爬虫 | ✅ 稳定 | 已安装 |

---

### 媒体技能 ⭐⭐

| 技能 | 说明 | 状态 | 安装 |
|------|------|------|------|
| **[Screenshot](#screenshot)** | 📸 截图 | ✅ 稳定 | 已安装 |
| **[FAL Image Edit](#fal-image-edit)** | 🖼️ 图片编辑 | ✅ 稳定 | 已安装 |

---

### 其他技能 ⭐⭐

| 技能 | 说明 | 状态 |
|------|------|------|
| **[Proxy](#proxy)** | 🌐 代理配置 | ✅ 稳定 |
| **[EvoClaw](#evoclaw)** | 🧬 EvoClaw | ✅ 稳定 |
| **[Moltron](#moltron)** | 🤖 Moltron | ✅ 稳定 |

---

## 📖 技能详情

### Guardian

**仓库**: https://github.com/openclaw-AI-make/openclaw-guardian

**功能**:
- ✅ 4 层健康检查（进程 + 端口+API+ 功能）
- ✅ 3 级恢复流程（轻量→强制→回滚）
- ✅ 5 分钟超时回滚保护
- ✅ 多通道通知（钉钉 + Telegram）
- ✅ 智能缓存清理

**安装**:
```bash
git clone https://github.com/openclaw-AI-make/openclaw-guardian.git
cd openclaw-guardian
```

**使用**:
```bash
oc-config-backup    # 配置备份
oc-backup           # 完整备份
oc-status           # 查看状态
```

---

### Disaster Recovery

**仓库**: https://github.com/openclaw-AI-make/openclaw-disaster-recovery

**功能**:
- ✅ NAS 备份（每天 3AM）
- ✅ 完整系统备份
- ✅ 灾难后恢复
- ✅ 备份验证测试

**安装**:
```bash
git clone https://github.com/openclaw-AI-make/openclaw-disaster-recovery.git
cd openclaw-disaster-recovery
```

**使用**:
```bash
bash backup.sh daily    # 每日备份
bash restore.sh         # 恢复系统
```

---

### Memory Isolation

**仓库**: https://github.com/openclaw-AI-make/openclaw-memory-isolation

**功能**:
- ✅ 15 类聚焦记忆
- ✅ 智能理解（简洁指令识别）
- ✅ 上下文优化（分层加载）
- ✅ 每日分析（趋势对比）

**安装**:
```bash
git clone https://github.com/openclaw-AI-make/openclaw-memory-isolation.git
cd openclaw-memory-isolation
```

**使用**:
```bash
bash add_memory.sh "关键词" "标题" "内容"
bash search.sh "关键词"
bash daily_summary.sh
```

---

### CLI

**仓库**: https://github.com/openclaw-AI-make/openclaw-cli

**功能**:
- ✅ OpenClaw 命令行工具
- ✅ 技能管理
- ✅ 配置管理

**安装**:
```bash
git clone https://github.com/openclaw-AI-make/openclaw-cli.git
cd openclaw-cli
```

---

### Config

**仓库**: https://github.com/openclaw-AI-make/openclaw-config

**功能**:
- ✅ 配置管理技能
- ✅ 配置验证
- ✅ 配置优化

**安装**:
```bash
git clone https://github.com/openclaw-AI-make/openclaw-config.git
cd openclaw-config
```

---

## 🎯 技能推荐

### 新手必备（3 个）

1. **Guardian** - 守护系统（必须）
2. **Memory Isolation** - 记忆系统（推荐）
3. **CLI** - 命令行工具（方便）

### 进阶技能（5 个）

1. **Disaster Recovery** - 灾备系统
2. **Config** - 配置管理
3. **SSH Hardening** - SSH 加固
4. **System Control** - 系统控制
5. **Automation** - 自动化

### 专业技能（按需）

- **开发**：Linux Server Expert, Nginx Optimizer
- **办公**：PDF, Excel, PPT
- **安全**：Clawsec, SSH Hardening
- **媒体**：Screenshot, FAL Image Edit

---

## 📚 相关资源

| 资源 | 链接 |
|------|------|
| 组织主页 | https://github.com/openclaw-AI-make |
| 快速入门 | quick-start.md |
| 最佳实践 | best-practices.md |
| 官方文档 | https://docs.openclaw.ai |

---

*最后更新：2026-03-07*
