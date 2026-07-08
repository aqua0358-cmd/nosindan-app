# 脳疲労診断アプリ — デプロイ手順 (Vercel)

## 構成
このアプリはビルド不要の静的1ファイルHTML(`index.html`)です。
外部API・サーバー・データベースへの依存はなく、すべてブラウザ内(React + インラインJS)で完結します。

## 環境変数
不要です。

## 起動コマンド / ビルドコマンド
不要です(静的ファイルをそのまま配信するだけ)。

## デプロイ手順(Vercel)
1. この `deploy/` フォルダの中身(`index.html`, `vercel.json`)をGitHubリポジトリのルートに置く
2. https://vercel.com で「Add New Project」→ そのリポジトリを選択
3. Framework Preset: **Other**
4. Build Command: 空欄のまま
5. Output Directory: `.` (ルート)
6. Deploy をクリック

## デプロイ先の候補
- **Vercel**(推奨・上記手順)
- Netlify(同様に静的ファイルをドラッグ&ドロップするだけで公開可能)
- GitHub Pages(リポジトリの `index.html` をそのまま公開)
- Cloudflare Pages

## 今後サーバー機能(問診結果の保存、ユーザー認証、外部予約API連携など)を追加する場合
現状はブラウザ完結のプロトタイプのため、以下が必要になります:
- バックエンドAPI(例: Vercel Serverless Functions / Next.js API Routes)
- データベース(例: Supabase, Vercel Postgres)
- その場合は環境変数(DB接続文字列など)をVercelのプロジェクト設定 → Environment Variablesに追加

現時点ではその必要はなく、このままVercelにアップロードするだけで公開できます。
