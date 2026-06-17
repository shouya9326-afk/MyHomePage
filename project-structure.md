# プロジェクト構成メモ

`my.homepage` フォルダにある各ファイル・フォルダの役割をまとめた学習用リファレンス。
ほとんどは `create-next-app`（Next.js公式の生成ツール）が自動生成したもの。

## ディレクトリツリー

```
my.homepage/                ← Gitリポジトリのルート ＝ Next.jsアプリ本体
├── package.json            ① プロジェクトの心臓部（定義・コマンド・依存）
├── package-lock.json       ② 依存関係の確定リスト（バージョン固定）
├── node_modules/           ③ ダウンロードされた部品庫（巨大・自動生成）
├── app/                    ④ ページの本体（App Router）
│   ├── layout.tsx          　 全ページ共通の枠組み
│   ├── page.tsx            　 トップページ（ / ）の中身
│   ├── globals.css         　 全体に効くCSS（Tailwind読み込み）
│   └── favicon.ico         　 ブラウザタブのアイコン
├── public/                 ⑤ 画像など静的ファイル置き場
│   └── *.svg               　 サンプル画像（next/vercel等）
├── tsconfig.json           ⑥ TypeScript の設定
├── next.config.ts          ⑦ Next.js の設定
├── next-env.d.ts           ⑧ TypeScript 型補助（自動生成・Git除外）
├── eslint.config.mjs       ⑨ ESLint（コード品質チェック）の設定
├── postcss.config.mjs      ⑩ PostCSS（Tailwind変換）の設定
├── .gitignore              ⑪ Git管理から除外する物のリスト
├── README.md               ⑫ リポジトリの説明書
├── AGENTS.md               ⑬ AI向けの注意書き
├── CLAUDE.md               ⑭ 開発ルール（手動作成）
├── project-structure.md    　 このファイル
├── .next/                  ⑮ ビルド結果（自動生成・一時的・Git除外）
└── .git/                   　 Gitの管理データ本体
```

## 各ファイルの詳細

| # | 名前 | 役割 | 生成方法 | Git管理 |
|---|------|------|----------|:-------:|
| ① | `package.json` | プロジェクト名・コマンド(`scripts`)・依存部品を定義する司令塔 | create-next-app（人も編集する） | ✅ |
| ② | `package-lock.json` | 全部品の正確なバージョンと入手先を固定する台帳。再現性を担保 | npm が自動生成（人は触らない） | ✅ |
| ③ | `node_modules/` | ①②を元に実際にダウンロードされた部品の本体。巨大 | `npm install` が自動生成 | ❌ 除外 |
| ④ | `app/` | ページとレイアウトを置く中心フォルダ（App Router方式） | create-next-app | ✅ |
| ④ | `app/layout.tsx` | 全ページ共通の外枠（`<html>`/`<body>` や共通レイアウト） | create-next-app | ✅ |
| ④ | `app/page.tsx` | トップページ（URL `/`）に表示される中身。**最初に編集する場所** | create-next-app | ✅ |
| ④ | `app/globals.css` | サイト全体に効くCSS。Tailwindをここで読み込む | create-next-app | ✅ |
| ④ | `app/favicon.ico` | ブラウザのタブに出る小さなアイコン | create-next-app | ✅ |
| ⑤ | `public/` | 画像・アイコンなど静的ファイルの置き場。URLで直接アクセスできる | create-next-app | ✅ |
| ⑥ | `tsconfig.json` | TypeScriptの動作設定。`@/*` のパス短縮なども定義 | create-next-app | ✅ |
| ⑦ | `next.config.ts` | Next.js自体の設定ファイル | create-next-app | ✅ |
| ⑧ | `next-env.d.ts` | Next.jsが型を効かせるための補助。**編集不要** | Next.jsが自動生成 | ❌ 除外 |
| ⑨ | `eslint.config.mjs` | コードの書き方ミスや品質を自動チェックするESLintの設定 | create-next-app | ✅ |
| ⑩ | `postcss.config.mjs` | CSSを変換する仕組み（Tailwindを動かす）の設定 | create-next-app | ✅ |
| ⑪ | `.gitignore` | Gitに含めない物のリスト（`node_modules` 等）。Next.js標準テンプレ | create-next-app | ✅ |
| ⑫ | `README.md` | リポジトリのトップに表示される説明書 | create-next-app | ✅ |
| ⑬ | `AGENTS.md` | AIツール向けの注意書き（このNext.jsは新しく仕様が違う旨） | create-next-app | ✅ |
| ⑭ | `CLAUDE.md` | このプロジェクトの開発ルール・進め方 | 手動作成 | ✅ |
| ⑮ | `.next/` | `npm run dev` / `build` 時に作られるビルド結果。消しても再生成される | Next.jsが自動生成 | ❌ 除外 |
| - | `.git/` | コミット履歴などGitの管理データ本体 | `git init` が生成 | （管理の仕組みそのもの） |

## 覚えておくと良いポイント

- **最もよく触る**: `app/page.tsx`（ページの中身）, `package.json`（コマンド・依存）
- **触ってはいけない/触らなくてよい**: `package-lock.json`, `node_modules/`, `next-env.d.ts`, `.next/`
- **Git除外（❌）の物**: 自動生成で復元できる or 環境依存のもの。リポジトリを軽く・きれいに保つため除外している
- 大半は `create-next-app` の自動生成物。**自分で1から作ったわけではない**点を理解しておくと、どこを編集すべきか迷わなくなる
