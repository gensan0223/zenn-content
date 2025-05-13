---
title: "Zenn CLIで技術ブログをサクサクmdで書く方法"
emoji: "📝"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["zenn", "cli", "github", "zenn-cli", "blog"]
published: true
---

Zenn CLIを使って、Zennの記事を**ローカルで書き、GitHubでバージョン管理する**環境を整えたので、その手順をまとめます。  
開発ログや技術記事をGitHub上で管理したい方にはおすすめです。

## ✅ 前提

- Node.js / npm がインストール済み
- GitHubアカウントがある
- Zennアカウントを作成済み（https://zenn.dev）

---

## 🛠 手順

### 1. リポジトリ作成

GitHubで `zenn-contents` などのリポジトリを新規作成。

```bash
git clone https://github.com/yourname/zenn-contents.git
cd zenn-contents
```

### 2. Zenn CLI をインストール
グローバルで入れるだけでOKです（ローカルでも可）。
```bash
# グローバルの場合
npm install -g zenn-cli
# ローカルの場合
npm init -y
npm install zenn-cli --save-dev
```

自分は`zenn-cli`をグローバルに入れたくなかったのでローカルで対応しました

### 3. Zenn CLI 初期化

```bash
zenn init
```

### 3. ローカルで記事を書く
以下のような構成になります：

```bash
.
├── articles/      # 記事（Markdown）
├── books/         # 書籍シリーズ用（任意）
└── zenn.config.json
```

### 4. 記事作成
対話式にタイトルなどを入力すれば、articles/ 以下にMarkdownファイルが作成されます。
```bash
# グローバル
zenn new:article
# ローカル
npx zenn new:article
# slugを指定したい場合
npx zenn new:article --slug my-article
```

### 5. ローカルプレビュー
```bash
# グローバル
zenn preview
# ローカル
npx zenn preview
```
http://localhost:8000 を開くと、Zennと同じ見た目で記事を確認できます。z


## 🧭 公開の流れ
1. 記事を書き終えたら `git add` → `commit` → `push`

2. Zennの GitHub連携ページ で対象リポジトリを登録

3. zenn.dev/ユーザー名/articles/スラッグ に反映されます

## 📝 補足Tips
- emoji や topics は Markdownの最初にYAML形式で設定

- .md ファイル名は slug（URLの一部）になります

- 複数記事をシリーズ化したい場合は books/ ディレクトリへ

## 🙋 こんな人におすすめ
- GitHubで記事を管理したい
- エディタ（VSCodeやNeovim）でMarkdownを書きたい
- 開発ログや試行錯誤を残したい

## 📌 まとめ
Zenn CLIを使えば、いつもの開発環境の中でZenn記事を管理できます。
GitHubでの履歴管理やコラボレーションもできるので、ポートフォリオとしての見せ方にもおすすめです。


## 📚 参考
- Zenn公式ドキュメント
- Zenn CLI GitHubリポジトリ


---

