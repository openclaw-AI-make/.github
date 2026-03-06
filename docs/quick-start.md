# OpenClaw 快速入门指南

> 5 分钟部署你的 AI 守护系统

---

## 🎯 部署目标

- ✅ Guardian 守护系统（实时监控 + 自动恢复）
- ✅ 配置备份（5 分钟回滚保护）
- ✅ 健康检查（每分钟自动）

**预计时间**：5-10 分钟

---

## 📋 前提条件

| 要求 | 说明 |
|------|------|
| **系统** | Ubuntu 22.04 / 24.04 |
| **Node.js** | 22+ |
| **OpenClaw** | 已安装并运行 |
| **网络** | 可访问 GitHub |

---

## 🚀 快速部署

### 第 1 步：克隆仓库

```bash
git clone https://github.com/openclaw-AI-make/openclaw-guardian.git
cd openclaw-guardian
```

### 第 2 步：配置通知（可选）

```bash
# 复制配置模板
cp notify.conf.example notify.conf

# 编辑配置
nano notify.conf
```

**填入 Telegram 信息**：
```bash
BOT_TOKEN="YOUR_BOT_TOKEN_HERE"
CHAT_ID="YOUR_CHAT_ID_HERE"
```

> 没有 Telegram？跳过这步，Guardian 也能正常工作。

### 第 3 步：配置 NAS 备份（可选）

```bash
# 复制配置模板
cp nas.conf.example nas.conf

# 编辑配置
nano nas.conf
```

**填入 NAS 信息**：
```bash
NAS_HOST="192.168.10.6"
NAS_USER="openclaw"
NAS_PASS="YOUR_NAS_PASSWORD_HERE"
NAS_DIR="/openclaw"
```

> 没有 NAS？跳过这步，本地备份也能用。

### 第 4 步：运行 Guardian

```bash
# 备份配置（首次运行）
oc-config-backup

# 查看状态
oc-status
```

**输出示例**：
```
✅ Guardian 守护系统运行正常
下次检查：1 分钟后
备份位置：~/.openclaw-backups/
```

---

## ✅ 验证部署

### 检查服务状态

```bash
# 查看 Guardian 状态
oc-status

# 查看日志
oc-logs
```

### 测试健康检查

```bash
# 手动运行检查
oc-watchdog

# 查看检查结果
cat /var/log/openclaw-watchdog.log
```

### 测试配置备份

```bash
# 备份当前配置
oc-config-backup

# 查看备份列表
oc-list
```

---

## 🔧 常用命令

| 命令 | 说明 |
|------|------|
| `oc-backup` | 完整系统备份 |
| `oc-restore <名称>` | 系统恢复 |
| `oc-config-backup` | 配置备份（5 分钟回滚） |
| `oc-confirm <时间戳>` | 确认配置（取消回滚） |
| `oc-rollback <时间戳>` | 手动回滚 |
| `oc-status` | 查看服务状态 |
| `oc-logs` | 查看日志 |
| `oc-watchdog` | 运行健康检查 |

---

## 🎯 下一步

### 配置 GitHub Secrets（推荐）

```
1. 访问 GitHub 仓库
2. Settings → Secrets and variables → Actions
3. 添加 Secrets:
   - BOT_TOKEN (Telegram)
   - NAS_PASS (NAS 密码)
   - GITHUB_TOKEN (GitHub Token)
```

### 配置自动启动

```bash
# 添加到 crontab
crontab -e

# 添加以下内容（每分钟检查）
* * * * * ~/.openclaw-protection/watchdog.sh
```

### 发布到 ClaWHub（可选）

```bash
# 安装技能
clawhub install openclaw-guardian
```

---

## 🆘 故障排除

### 问题 1：服务无法启动

```bash
# 检查服务状态
oc-status

# 查看日志
oc-logs

# 清理缓存后重试
oc-cache-clean full
```

### 问题 2：备份失败

```bash
# 验证备份
oc-verify <备份名称>

# 检查磁盘空间
df -h
```

### 问题 3：通知不发送

```bash
# 检查配置
cat notify.conf

# 测试通知
./scripts/notify.sh test
```

---

## 📚 相关资源

| 资源 | 链接 |
|------|------|
| Guardian 仓库 | https://github.com/openclaw-AI-make/openclaw-guardian |
| 完整文档 | https://github.com/openclaw-AI-make/.github/tree/main/docs |
| 问题反馈 | https://github.com/openclaw-AI-make/openclaw-guardian/issues |

---

## 🎉 部署完成！

**你现在拥有**：
- ✅ 每分钟自动健康检查
- ✅ 配置修改前自动备份
- ✅ 5 分钟超时自动回滚
- ✅ 服务崩溃自动恢复
- ✅ 多通道故障通知

**Guardian 正在守护你的 OpenClaw！** 🦞
