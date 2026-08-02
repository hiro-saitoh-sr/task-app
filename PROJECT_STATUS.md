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
- 業務監査員Ver.0は実行履歴上、安定稼働中
- Firebase Authenticationの許可対象は業務用アカウント2件（Firebase側で管理）
- CodexとClaude Codeは対等な開発担当であり、共通Git手順と競合停止ルールを適用する

## 直近の変更
- AI引継ぎ資料とGit除外設定を整備
- Claude CodeとCodexを対等な開発担当として明記
- Git作業開始・終了、競合停止、利用者承認ルールを統一

## デプロイ・公開状況
- 公開URL: https://hiro-saitoh-sr.github.io/task-app/
- 今回は管理文書とGit除外設定のみを変更し、アプリ、Firebase、GAS、データは変更しない

## 検証結果
- `git fetch origin` 後、作業開始時にローカルと `origin/main` の一致を確認
- 文書変更のためアプリ動作確認は対象外
- `kanshain_v0` は毎日8:30頃に実行され、2026-07-05から2026-07-11まですべて正常完了、エラーなし
- `checkNewNotifications` は毎日8:47頃に実行され、確認した実行履歴はすべて正常完了

## 既知の課題
- 業務監査員Ver.0の正本はGASエディタ上にあり、GitHub管理されていない
- Google Chat Webhookのスクリプトプロパティ移行は、稼働安定後に対応する保留課題

## 2026年8月3日 実施内容
- 年更・算定画面の「対象年度」が改行される問題を修正（index.html 2626行目のtdにwhitespace-nowrapを追加）
- 36協定通知の改善
  - 起算日を過ぎた顧問先を通知から非表示
  - 手続き済・納品済の場合、起算日の横にステータスバッジを表示
- 月変チェック新規追加モーダルを編集モーダルと項目統一
  - 追加項目：No・チェック対象者・手続き対象者・改定人数・ステータス・請求額
  - ステータス初期値：依頼受付
  - 請求額はisHiro制御（hiro@saitoh-sr.comのみ表示）
- データ一括出力機能を追加
  - ボタンラベル：📥 データ一括出力
  - 出力形式：Excel（.xlsx）
  - シート構成：案件管理・月変チェック・年更算定・給与計算・顧問先マスタ
  - 案件管理は請求済・取消済を除外
  - 給与計算は全年月フラット化で出力
  - 請求金額は含めない
  - 全アカウントに表示

## NEXT_ACTION
- 次回作業開始時に `git fetch origin`、指示文書、Git状態を再確認する

## 最終更新
- 最終更新AI: Claude Code
- 最終更新日時: 2026-08-03（日本時間）
