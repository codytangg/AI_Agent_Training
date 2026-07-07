# MEMORY

> Agent 的長期記憶（跨 session 保留的重要資訊）

---

## 環境

- OS：WSL (Ubuntu)
- Shell：bash (~/.bashrc)
- AI Agent：Hermes
- Config：~/.hermes/config.yaml
- GitHub：codytangg (https://github.com/codytangg/AI_Agent_Training)

## 安全設定

- approvals.mode: manual（每步都問）
- security.redact_secrets: true（自動遮蔽 password/key）
- security.tirith_enabled: true（安全掃描器）
- gh CLI 已安裝在 ~/gh-cli/bin/

## 學員偏好

- 用繁體中文溝通
- Beginner 友善，步驟要清晰
- 不用 sudo / rm -rf / force delete
- 先解釋再執行，等確認才動手
