# claude-config

全プロジェクト共通の Claude Code 設定(ユーザー単位の CLAUDE.md と、そこから読み込むガイド類)。

## ファイル

- `CLAUDE.md` — 全プロジェクト共通の指示。各PCの `~/.claude/CLAUDE.md` から読み込む
- `japanese-style-guide.md` — 日本語の書き方ガイド(直訳・硬い表現の言い換え表)。`CLAUDE.md` から読み込む

## 新しいPCでのセットアップ

PowerShell で次を実行する。

```powershell
git clone https://github.com/maki-rs2/claude-config.git "$HOME\claude-config"
New-Item -ItemType Directory -Force "$HOME\.claude" | Out-Null
Set-Content -Path "$HOME\.claude\CLAUDE.md" -Value '@~/claude-config/CLAUDE.md' -Encoding ascii
```

`~/.claude/CLAUDE.md` がすでにある場合は、上書きせずに中身をこのリポジトリの `CLAUDE.md` へ移してから実行する。

## 更新

どのPCで編集しても、`git push` したあと他のPCで `git pull` すれば反映される。Claude Code は起動時に読み込むので、反映後は新しいセッションを開始する。
