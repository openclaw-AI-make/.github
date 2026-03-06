# OpenClaw 备份监控系统

OpenClaw Gateway 自动备份与恢复系统。

## 功能特性

- 📝 配置文件变更自动备份（保留最近3份）
- ⚠️ Gateway 异常自动检测与恢复
- 🔔 Telegram 通知
- 🚀 开机自动启动（cron）

## 快速开始

```bash
# 1. 解压
tar -xzvf openclaw-backup-monitor.tar.gz

# 2. 编辑配置文件
nano openclaw-backup-monitor/config.env
# 必须配置:
#   BOT_TOKEN="你的Telegram Bot Token"
#   CHAT_ID="你的Telegram Chat ID"

# 3. 安装
bash openclaw-backup-monitor/install.sh
```

## 配置说明

安装前必须编辑 `config.env`:

| 变量 | 说明 | 必需 |
|------|------|------|
| BOT_TOKEN | Telegram Bot Token | ✅ 是 |
| CHAT_ID | Telegram Chat ID | ✅ 是 |
| BACKUP_DIR | 备份目录 | 可选 |
| CONFIG_DIR | OpenClaw 配置目录 | 可选 |

### 获取 Telegram 凭证

- **Bot Token**: 在 Telegram 联系 @BotFather，使用 /newbot
- **Chat ID**: 在 Telegram 联系 @userinfobot 或 @getidsbot

## 文件说明

```
openclaw-backup-monitor/
├── config.env      # 配置文件 (必须修改)
├── install.sh      # 安装脚本
├── uninstall.sh    # 卸载脚本
├── backup.sh      # 备份脚本
├── restore.sh     # 恢复脚本
├── monitor.sh     # 监控脚本
└── backups/      # 备份存储
```

## 手动命令

```bash
# 手动备份
bash ~/Desktop/backup-openclaw/backup.sh

# 手动恢复
bash ~/Desktop/backup-openclaw/restore.sh

# 查看日志
tail -f ~/Desktop/backup-openclaw/backup.log
tail -f ~/Desktop/backup-openclaw/restore.log
```

## 卸载

```bash
bash openclaw-backup-monitor/uninstall.sh
```

## 许可证

MIT
