# OpenClaw 最佳实践

> 使用技巧和最佳实践总结

---

## 🔒 隐私安全

### 敏感信息处理

**✅ 推荐做法**：
```bash
# 使用占位符
BOT_TOKEN="YOUR_BOT_TOKEN_HERE"
NAS_PASS="YOUR_NAS_PASSWORD_HERE"

# 使用 GitHub Secrets
${{ secrets.BOT_TOKEN }}

# 使用 .private 目录
~/.private/credentials/nas.conf
chmod 600 ~/.private/credentials/nas.conf
```

**❌ 避免做法**：
```bash
# 不要硬编码真实凭证
BOT_TOKEN="8423301827:AAG13bhK41bJINB4iaE-xQWMqYWODdb6XRw"  # ❌

# 不要提交到 Git
git add .private/  # ❌
```

### 提交前检查

```bash
# 运行隐私清理
./scripts/sanitize-for-github.sh

# 检查敏感文件
find . -name "*.conf" -not -name "*.example" -not -path "./.private/*"

# 搜索敏感内容
grep -r "BOT_TOKEN=" . --exclude-dir=.private --exclude-dir=.git
```

---

## 🛡️ Guardian 使用技巧

### 配置修改流程

```bash
# 1. 备份配置（启动 5 分钟回滚保护）
oc-config-backup

# 2. 修改配置
nano ~/.openclaw/openclaw.json

# 3. 重启服务
systemctl --user restart openclaw-gateway

# 4. 测试正常后确认
oc-confirm <时间戳>

# 如果服务崩溃，自动回滚
```

### 健康检查优化

```bash
# 查看检查日志
cat /var/log/openclaw-watchdog.log

# 手动运行检查
oc-watchdog

# 调整检查频率（可选）
nano ~/.config/systemd/user/openclaw-guardian.timer
# 修改 OnUnitActiveSec=1min
```

### 缓存清理策略

```bash
# 轻量清理（锁文件）
oc-cache-clean light

# 中等清理（会话缓存）
oc-cache-clean medium

# 完全清理（所有缓存）
oc-cache-clean full

# 核弹清理（包括凭证）
oc-cache-clean nuclear  # ⚠️ 慎用！
```

---

## 📦 备份策略

### 本地备份

| 类型 | 频率 | 保留时间 |
|------|------|---------|
| 配置备份 | 变化时 | 最近 10 个 |
| 完整备份 | 每天 | 最近 7 天 |

### NAS 备份

| 类型 | 频率 | 保留时间 |
|------|------|---------|
| 日备 | 每天 3AM | 30 天 |
| 周备 | 每周日 | 12 周 |
| 月备 | 每月 1 日 | 12 月 |

### 备份验证

```bash
# 验证备份完整性
oc-verify <备份名称>

# 测试恢复（每月）
bash test-restore.sh
```

---

## 🧠 记忆系统优化

### 15 类聚焦记忆

**高频类**（常用）：
- `programming` - 编程开发
- `server_mgmt` - 服务器管理
- `prompt_engineering` - 提示工程

**中频类**：
- `devops` - 运维自动化
- `security` - 安全加固
- `content_writing` - 内容创作

**普通类**：
- `social_media`, `ppt_creation`, `excel`, ...

### 添加记忆

```bash
# 自动归类
bash add_memory.sh "NAS 配置" "群晖 NAS 备份配置" "
- NAS 地址：192.168.10.6
- 用户：openclaw
- 密码：TqleHG
- 路径：/openclaw
"
```

### 搜索记忆

```bash
# 关键词搜索
bash search.sh "GitHub"

# 分类搜索
bash search.sh --category programming

# 时间范围搜索
bash search.sh --since 2026-03-01
```

---

## 📊 性能优化

### Token 消耗优化

| 优化前 | 优化后 | 节省 |
|--------|--------|------|
| 加载全部记忆 | 分层加载 | -60% |
| 无分类检索 | 15 类聚焦 | -40% |
| 重复内容 | 缓存复用 | -30% |
| **总计** | | **-40%** |

### 上下文管理

```
分层加载策略：
├── Layer 1: 人格设定 (必加载)
├── Layer 2: 今日记忆 (必加载)
├── Layer 3: 长期记忆 (选择性)
└── Layer 4: 历史记忆 (按需)
```

**总大小控制**：~1500 tokens

---

## 🔧 故障排除

### Gateway 无法启动

```bash
# 1. 检查服务状态
systemctl --user status openclaw-gateway

# 2. 查看日志
journalctl --user -u openclaw-gateway -f

# 3. 清理缓存
oc-cache-clean full

# 4. 重启服务
systemctl --user restart openclaw-gateway
```

### 备份失败

```bash
# 1. 验证备份
oc-verify <备份名称>

# 2. 检查磁盘空间
df -h

# 3. 检查 NAS 连接
ping 192.168.10.6

# 4. 查看备份日志
cat ~/.openclaw/workspace/backup/disaster_recovery/backup_log.txt
```

### 通知不发送

```bash
# 1. 检查配置
cat notify.conf

# 2. 测试通知
./scripts/notify.sh test

# 3. 检查网络连接
curl https://api.telegram.org

# 4. 查看通知日志
cat /var/log/openclaw-notify.log
```

---

## 📝 日常维护

### 每日检查

```bash
# 查看 Guardian 状态
oc-status

# 查看备份状态
oc-list

# 查看监控日志
tail -20 /var/log/openclaw-watchdog.log
```

### 每周检查

```bash
# 清理过期备份
bash cleanup-nas.sh

# 检查系统日志
journalctl --user -u openclaw-gateway --since "1 week ago"
```

### 每月检查

```bash
# 测试恢复
bash test-restore.sh

# 整理长期记忆
# 更新 MEMORY.md
```

---

## 🎯 技能推荐组合

### 新手组合

```
Guardian + Memory Isolation + CLI
```

**用途**：基础守护 + 记忆 + 命令行

### 开发组合

```
Guardian + Linux Server Expert + SSH Hardening + Automation
```

**用途**：服务器开发 + 自动化

### 办公组合

```
Guardian + PDF + Excel + PPT + Email Processor
```

**用途**：办公自动化

### 安全组合

```
Guardian + SSH Hardening + Clawsec + System Control
```

**用途**：系统安全加固

---

## 📚 相关资源

| 资源 | 链接 |
|------|------|
| 快速入门 | quick-start.md |
| 技能索引 | skills-index.md |
| 官方文档 | https://docs.openclaw.ai |
| GitHub 组织 | https://github.com/openclaw-AI-make |

---

*最后更新：2026-03-07*
