# task-app プロジェクト

## プロジェクト概要
社会保険労務士齊藤事務所の業務タスク管理システム。
案件管理・請求集計・月変チェック・年更算定・給与計算の機能を持つ。

## 公開URL・リポジトリ
- 公開URL: https://hiro-saitoh-sr.github.io/task-app/
- リポジトリ: https://github.com/hiro-saitoh-sr/task-app

## 技術スタック
- HTML/CSS/JavaScript（フレームワークなし）
- Firebase Realtime Database
- Firebase Authentication（メール認証）

## Firebase設定
- プロジェクトID: task-app-493716
- リージョン: asia-southeast1
- DB URL: https://task-app-493716-default-rtdb.asia-southeast1.firebasedatabase.app
- ログイン許可アカウント:
  - hiro@saitoh-sr.com
  - kawahara@saitoh-sr.com

## データ構造（Firebase Realtime Database）
- `cases`: 案件データ（顧客名・手続き内容・ステータス等）
- `masters`: 顧問先マスタ（36協定起算日等含む）
- `masters/customers`: 顧問先一覧
- `billingSnapshots`: 請求スナップショット（月別・確定後保存）
- `payrolls`: 給与計算データ
- `payrollRates`: 給与単価設定
- `checks`: 月変チェック等

## 開発方針
- 修正はすべてClaude Codeへの指示文として受け取る
- F12デバッグや直接コード修正は不要
- 修正後は必ず `git add . && git commit && git push` を実行
- コミットメッセージは日本語で「feat: 」「fix: 」等のプレフィックスを付ける
- ステップごとに確認しながら進める

## 注意事項
- 事務所の要のシステムのため、既存データに影響する変更は慎重に行う
- Firebase Rulesは変更しない（cases・mastersは.read: true、書き込みは認証必須）
- 変更時はブラウザで動作確認してから push
- 個人名は使用しない（「正社員さん」「パートさん」で統一）

## 主な機能
- 案件管理（新規登録・編集・ステータス変更）
- 対象年月/年月日での案件管理（日は任意入力）
- 絞り込みフィルター（顧客名・手続き・担当者・ステータス・対象年月）
- 請求集計（月別、対象年月で絞り込み）
- 月変チェック
- 年更算定
- 給与計算（段階単価・固定額対応）

## 業務監査員Ver.0との連携
- 業務監査員GASがcasesとmastersを参照する
- 毎朝8時にGoogle Chatへ通知
- 監査項目:
  - 対象年月超過案件
  - 36協定期限接近
  - 年更・算定 依頼待ち
  - 新規登録案件
  - 対象日到来リマインダー
  - 対象日超過案件

## 関連プロジェクト
- shogu-app: 処遇改善加算タスク管理システム（casesと同じDBを使用）
- estimate-contract-app: 見積書・契約書作成アプリ
