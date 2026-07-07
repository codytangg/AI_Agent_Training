# 安全狀態紀錄

> 建立日期：2026-07-07
> 環境：WSL (Ubuntu) + Hermes Agent + bash

---

## 安全三件套對照

### 第一層：垃圾桶保護

| 項目 | 狀態 |
|------|------|
| trash 工具 | ❌ 未安裝 |
| rm alias | ❌ 未設定 |
| 備選方案 | 待決定：trash-cli (pip) 或自製 bash function |

### 第二層：危險指令黑名單

| 項目 | 狀態 |
|------|------|
| Tirith 安全掃描器 | ✅ 已啟用 (security.tirith_enabled: true) |
| secrets 自動遮蔽 | ✅ 已啟用 (security.redact_secrets: true) |
| 20 條具體黑名單 | ❌ Hermes 暫無等效的逐條 deny 設定 |

已啟用的內建保護：
- security.redact_secrets: true（password/key 自動遮蔽）
- security.tirith_enabled: true（內建安全掃描器）
- security.tirith_path: tirith（位於 ~/.hermes/bin/tirith）

### 第三層：權限模式

| 項目 | 狀態 |
|------|------|
| approvals.mode | ✅ manual（最謹慎，每步都問） |
| approvals.cron_mode | ✅ deny（自動排程被拒絕） |

等同於文件中的 Default 模式 — AI 做任何事都會先問。

---

## 不適用的設定（Mac / Claude Code 專用）

| 項目 | 原因 |
|------|------|
| brew install trash | Homebrew 是 Mac 工具，WSL 不適用 |
| ~/.claude/settings.json | 使用 Hermes，不是 Claude Code |
| jq 合併 deny 規則 | 無對應的 settings.json |

---

## 待跟進事項

1. [ ] 決定垃圾桶保護方案（trash-cli vs 自製 bash function）
2. [ ] 研究 Hermes 是否支援具體指令黑名單
3. [ ] 熟悉安全 command：pwd, ls, mkdir -p, cd
4. [ ] 認識 stop signals：sudo, rm, force, reset, credential

---

## 環境資訊

| 項目 | 值 |
|------|-----|
| Shell | bash (~/.bashrc) |
| OS | WSL (Ubuntu) |
| AI Agent | Hermes |
| Config | ~/.hermes/config.yaml |
| Python | python3 (/usr/bin/python3) |
| jq | 未安裝 |
