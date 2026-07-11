# task-app PROJECT STATUS

## 正本
- ソースコード: GitHubリポジトリ `hiro-saitoh-sr/task-app`
- 本番公開先: GitHub Pages
- 本番データ: Firebase Realtime Database

## Git状態
- 対象ブランチ: `main`
- 整備開始時の基準コミット: `ad97afa`
- 2026-07-11確認時点で `origin/main` と同期済み（ahead 0 / behind 0）

## 現在の実装状況
- 案件管理、請求集計、月変チェック、年更算定、給与計算を実装
- 業務監査員Ver.0が `cases` と `masters` を参照
- Firebase Authenticationの許可対象は業務用アカウント2件（Firebase側で管理）

## 直近の変更
- AI引継ぎ資料とGit除外設定を整備
- Claude CodeとCodexを対等な開発担当として明記

## デプロイ・公開状況
- 公開URL: https://hiro-saitoh-sr.github.io/task-app/
- 今回は管理文書とGit除外設定のみを変更し、アプリ、Firebase、GAS、データは変更しない

## 検証結果
- `git fetch origin` 後、作業開始時にローカルと `origin/main` の一致を確認
- 文書変更のためアプリ動作確認は対象外

## 既知の課題
- 業務監査員Ver.0の正本はGASエディタ上にあり、GitHub管理されていない

## NEXT_ACTION
- 次回作業開始時に `git fetch origin`、指示文書、Git状態を再確認する

## 最終更新
- 最終更新AI: Codex
- 最終更新日時: 2026-07-11（日本時間）
