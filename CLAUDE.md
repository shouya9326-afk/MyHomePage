# my.homepage — ポートフォリオサイト

就職活動用のポートフォリオサイト。言語・共通ルールは親の `CLAUDE.md` を参照。

## 技術スタック

- **Next.js** (App Router) + **TypeScript**
- **Tailwind CSS**
- デプロイ: **Vercel**
- リポジトリ: **GitHub**

## ディレクトリ構成

このフォルダ（`my.homepage`）自体がGitリポジトリのルート兼Next.jsアプリ本体。

```
my.homepage/           ← Gitルート ＝ Next.jsアプリ
  ├── CLAUDE.md          ← このファイル
  ├── app/               ← ページ・レイアウト（App Router）
  ├── public/            ← 画像など静的ファイル
  └── package.json       ← 依存パッケージ・スクリプト定義
```

## 開発コマンド

```bash
npm run dev    # 開発サーバー起動 → http://localhost:3000
npm run build  # 本番ビルド
npm run lint   # ESLint実行
```

## セットアップ状況

- [x] フォルダ作成済み
- [x] Node.js インストール（v24.16.0 / npm 11.13.0）
- [x] Next.js プロジェクト作成（TypeScript + Tailwind + ESLint + App Router）
- [x] GitHub連携（リモート: shouya9326-afk/MyHomePage）
- [ ] Vercel デプロイ設定

### 環境メモ

- ネットワークのSSL検査により `npm` で証明書エラーが出る場合は
  `NODE_OPTIONS=--use-system-ca` を付けて実行する
  （例: `NODE_OPTIONS=--use-system-ca npm install`）

## ページ構成

| セクション | 内容 |
|----------|------|
| Hero | 名前・キャッチコピー・SNSリンク（GitHub等） |
| About | 自己紹介・経歴・学習中の技術 |
| Skills | 技術スタック（アイコン付き） |
| Works | 制作物・個人プロジェクト |
| Contact | 連絡先 |
