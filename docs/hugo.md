# Hugo の使い方

Hugoの基本的な使い方まとめです。

詳細については、[公式ドキュメント](https://gohugo.io/documentation/)を参照してください。


## 環境構築

### レポジトリのクローン
```bash
git clone https://github.com/BraiDyn-BC/bdbc-website.git
```

### Hugoのインストール
```bash
brew install hugo
```

### Node.jsのインストール
```bash
brew install anyenv
anyenv init
```
表示されたコマンドを設定ファイルに追加してTerminalのウインドウを新しく開いて下記のコマンドを実行します。
```bash
anyenv install nodenv
cd bdbc-website
nodenv install
npm install
```

### ローカルサーバーを起動して確認
```bash
hugo server -D
```
- サーバーが起動し、`http://localhost:1313` でサイトを確認できます。
- ファイルの変更は即時に反映されます。


## 設定の変更

### 基本設定

`config/_default/hugo.toml` ファイルで以下のような項目の設定を行うことができます：
- サイトタイトル (`title`)
- 言語 (`languageCode`)

### 多言語設定

`config/_default/languages.toml` ファイルで多言語対応の設定を行います。

### メニュー設定

`config/_default/menus.toml` ファイルでナビゲーションメニューを定義します。
`weight`を設定することで表示される順番を制御することができます。

例:
```toml
[[main]]
  name = "Home"
  url = "/"
  weight = 1
```


## コンテンツの追加

### データベースの追加

1. `content/database/` ディレクトリに新規フォルダを作成します。
2. 作成したフォルダ内に `index.md` または言語別ファイル (`index.ja.md` や `index.en.md`) を作成します。
3. 画像などを表示させたい場合は、作成したフォルダに追加します。
4. 追加したMarkdownファイルの先頭に以下のようにフロントマターを設定します。

```markdown
---
title: "データベースタイトル"
date: 2024-01-01
draft: false
tags: [Database, Sample]
images: [image.png] # ここで設定した画像がデータベース一覧ページで表示されます
description: "ここの説明文がデータベース一覧ページで概要文として表示されます"
---
```

### ページの追加

1. 以下のコマンドを実行して新しいページを作成します。
   ```bash
   hugo new content/my-new-page.md
   ```
2. 作成されたファイルを編集します。
3. フロントマターを設定してページメタデータを管理します。


## レイアウトの修正

### スタイルの変更

[`assets/sass/styles.scss`](../assets/sass/styles.scss) ファイルにカスタムスタイルを追加します。
SCSSの詳細については、[Sassの公式ドキュメント](https://sass-lang.com/documentation/syntax/)を参照してください。


## デプロイ方法

mainブランチに変更をプッシュすると、GitHub Actionsが自動的にデプロイを実行します。
デプロイの完了まで数分程度かかります。

```bash
git add .
git commit -m "変更内容のコメント"
git push origin main
```
