[README.md](https://github.com/user-attachments/files/30927007/README.md)
# 日用品ストック — 設置手順（GitHub Pages）

スマホのホーム画面に置いて使うWebアプリです。データは開いた端末の中だけに保存されます。

## 1. リポジトリを作る

GitHubで新しいリポジトリを作成します。

- 名前：`nichiyohin`（何でも構いません）
- 公開設定：**Public**
  - GitHub Pagesを無料で使うにはPublicが必要です。
  - リポジトリが公開されるのは「アプリのファイル」だけで、登録した日用品のデータは端末の中にしか存在しません。他人がURLを開いても、その人の空のリストが表示されるだけです。

## 2. ファイルをアップロードする

作ったリポジトリの「Add file」→「Upload files」で、以下6つをまとめてドラッグします。

```
index.html
manifest.webmanifest
sw.js
icon-192.png
icon-512.png
icon-512-maskable.png
apple-touch-icon.png
```

そのまま「Commit changes」を押します。

## 3. Pagesを有効にする

リポジトリの **Settings** → 左メニューの **Pages** を開きます。

- Source：`Deploy from a branch`
- Branch：`main` / `/ (root)`
- Save

1〜2分待つと、同じ画面にURLが出ます。

```
https://<ユーザー名>.github.io/nichiyohin/
```

## 4. ホーム画面に追加する

**iPhone（Safariで開くこと）**
共有ボタン → 「ホーム画面に追加」

Chromeなど他のブラウザからでは追加できません。必ずSafariで開いてください。

**Android（Chrome）**
右上のメニュー → 「ホーム画面に追加」または「アプリをインストール」

追加後はアイコンから直接起動し、ブラウザのアドレスバーは出ません。一度開いておけば、電波のない場所でも起動します。

## データについて

- 保存先は端末のブラウザ内（localStorage）です。サーバーには何も送られません
- **ホーム画面のアイコンから開いた場合と、Safariでそのまま開いた場合とでデータが別々になることがあります。** ホーム画面に追加したら、そちらだけを使ってください
- ブラウザの履歴やサイトデータを消すと、登録内容も消えます
- 一覧画面の下にある「書き出す」でJSONファイルとして保存できます。機種変更や、消えてしまったときはそのファイルを「読み込む」で戻せます

## 更新したいとき

`index.html` を差し替えて再アップロードすれば反映されます。すぐ変わらない場合は、`sw.js` の1行目にあるキャッシュ名の末尾の数字を1つ増やして（現在は `nichiyohin-v3`）から上げ直してください。
