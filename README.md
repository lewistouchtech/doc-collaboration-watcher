# Doc-Collaboration-Watcher v1.0

**协作文档实时监控技能**

---

## 📋 技能概述

实时监控协作文档变更，自动通知所有相关子代理和沟通通道，确保多代理协作信息同步。

**首创功能**：
- ✅ 文件变更实时监控（<5 秒）
- ✅ 全通道自动通知（飞书/微信/iMessage/WebChat）
- ✅ 冲突解决机制（子代理评审）
- ✅ 版本历史记录

---

## 🎯 适用场景

- 多代理协作项目（固件 + 前端 + 后端）
- 跨团队接口对齐
- 分布式文档维护
- 需要实时同步的协作场景

---

## 📦 安装

```bash
# 方法 1：OpenClaw 技能市场（推荐）
openclaw skills install doc-collaboration-watcher

# 方法 2：手动安装
cd ~/.openclaw/workspace/skills
git clone https://github.com/lewistouchtech/doc-collaboration-watcher.git
```

---

## 🚀 快速开始

### 1. 配置监控目录

```json
// config.json
{
  "workspace": "/Users/bot-eva/.openclaw/workspace",
  "docs_dir": "docs",
  "watched_files": [
    "esp32-collaboration.md",
    "esp32-collaboration-discussion.md"
  ],
  "notification": {
    "channels": ["feishu", "wechat", "imessage", "webchat"],
    "response_timeout_minutes": 5
  }
}
```

### 2. 启动监控

```bash
# 后台运行
python3 bin/doc-watcher.py &

# 或使用 OpenClaw
openclaw skills enable doc-collaboration-watcher
```

### 3. 测试通知

```bash
# 修改监控文件
echo "# 测试变更" >> docs/esp32-collaboration.md

# 观察通知输出
```

---

## 📊 功能特性

### 实时监控
- 文件变更检测（<5 秒）
- 文件哈希计算
- 变更历史记录

### 全通道通知
- 飞书通道
- 微信通道
- iMessage 通道
- WebChat 会话

### 冲突解决
- 双方讨论（30 分钟）
- 子代理评审
- 上报老板决策

### 版本管理
- 版本记录表
- 变更内容追踪
- 历史版本查询（Git）

---

## 🔧 配置说明

### config.json

```json
{
  "workspace": "/Users/bot-eva/.openclaw/workspace",
  "docs_dir": "docs",
  "log_dir": "logs",
  "watched_files": [
    "esp32-collaboration.md",
    "esp32-collaboration-discussion.md"
  ],
  "notification": {
    "channels": ["feishu", "wechat", "imessage", "webchat"],
    "response_timeout_minutes": 5,
    "evaluation_timeout_minutes": 30
  },
  "agents": [
    {"name": "伊娃 - 固件", "role": "firmware"},
    {"name": "伊娃 - 前端", "role": "frontend"},
    {"name": "伊娃 - 后端", "role": "backend"}
  ],
  "integration": {
    "memory_plus": {
      "enabled": false,
      "store_changes": false
    }
  }
}
```

---

## 📈 监控指标

### 变更统计
- 每日变更次数
- 各文件变更频率
- 平均变更大小

### 响应统计
- 确认率（5 分钟内）
- 评估及时率（30 分钟内）
- 超时次数

---

## 🤝 协作流程

```
1. 伊娃 A 修改文档
   ↓
2. 监控系统检测到变更（<5 秒）
   ↓
3. 自动通知所有通道和代理
   ↓
4. 各代理确认收到（5 分钟内）
   ↓
5. 相关代理评估影响（30 分钟内）
   ↓
6. 需要配合 → 调整工作计划
   ↓
7. 有分歧 → 子代理评审 → 老板决策
```

---

## 🧪 测试计划

### 阶段 1：基础监控
- [x] 文件修改检测
- [x] 文件创建检测
- [x] 哈希计算正确
- [x] 变更历史记录

### 阶段 2：通知功能
- [ ] 飞书通知
- [ ] 微信通知
- [ ] iMessage 通知
- [ ] WebChat 通知

### 阶段 3：响应追踪
- [ ] 确认状态追踪
- [ ] 超时提醒
- [ ] 统计报告

---

## 📝 版本记录

| 版本 | 日期 | 变更 | 作者 |
|------|------|------|------|
| v1.0 | 2026-04-07 | 初始版本 | 伊娃 |

---

## 🔗 相关链接

- **GitHub**: https://github.com/lewistouchtech/doc-collaboration-watcher
- **ClawHub**: https://clawhub.ai/skills/doc-collaboration-watcher
- **文档规范**: `/Users/bot-eva/.openclaw/workspace/docs/DOCUMENT-STANDARD.md`

---

## 📄 许可证

MIT License

---

*本技能由伊娃开发，用于多代理协作文档实时监控*
