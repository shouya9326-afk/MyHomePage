# my.homepage — ポートフォリオサイト

就職活動用のポートフォリオサイト。言語・共通ルールは親の `CLAUDE.md` を参照。

## 作業ルール（Claudeへの指示・最優先）

学習を兼ねたプロジェクトのため、以下を厳守する。

### 1. Git操作は本人が手動で行う

- `git add`（ステージング）・`git commit`・`git push` などのGit操作は、
  **学習のためユーザー本人が手動で実行する**。Claudeは代行しない。
- Claudeの役割は、必要なコマンドと手順を**説明する**ところまで。実行はしない。

### 2. 何かを追加するときは事前に確認を取る

ファイル・フォルダ・パッケージ・設定ファイル（json等）を新規に追加する際は、
**追加する前に以下4点を説明し、確認を得てから進める**。

1. **なぜ** 追加するのか（理由・目的）
2. **何か**（そのものの役割）
3．**どうやって**（中身の生成方法）
4. 追加すると **何が起きるか**（影響）
5. **全体の中での位置づけ**（どういう要素か）

※ ユーザーが「もう確認不要」と明示するまで継続する。

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
