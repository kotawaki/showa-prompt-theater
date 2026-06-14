# 公開用エピソードHTML

このフォルダには、公開する各話のHTMLを保存します。第1話を公開済みです。

## ファイル名

`ep001.html`、`ep002.html` のように、3桁の連番を使用します。

## HTMLの基本構造

- 共通CSSは `../style.css` を読み込む。
- 1ページ目から4ページ目までは `.episode-page` を使用し、縦書きで表示する。
- 5ページ目は `.episode-page.learning-page` を使用し、横書きで表示する。
- 5ページを `.episode-reader` で囲み、スマホで横方向にページ送りできるようにする。
- キャラ画像には `.character-visual` または `.episode-illustration` を使用する。
- 4コマ画像を追加する場合は `.comic-panel` を使用する。
- 前後の話とトップページへのナビゲーションを設置する。

## 公開時の更新箇所

1. このフォルダへエピソードHTMLを追加する。
2. `../index.html` のエピソード欄へリンクを追加する。
3. 必要に応じて `../prompts.html` と `../glossary.html` を更新する。

## 第1話の公開手順

1. `../../episodes_md/ep001_shinjin_ai_haizoku.md` の内容が確定していることを確認する。
2. `ep001.html` を作成し、ページタイトルと概要を設定する。
3. トップへ戻るリンクは `../index.html`、共通CSSは `../style.css` を指定する。
4. 5つの `.episode-page` に、原稿の各ページを一つずつ対応させる。
5. 第5ページだけに `.learning-page` を追加する。
6. `../index.html` から `episodes/ep001.html` へリンクする。
7. ファイルを直接移動しても壊れないよう、リンクと画像は相対パスで指定する。

## 画像と4コマ版の追加

- キャラクター画像は `../assets/images/characters/` に配置する。
- 話ごとの画像は `../assets/images/episodes/ep001/` のように分ける。
- 挿絵には `.episode-illustration`、4コマ画像には `.comic-panel` を使用する。
- 文章版と漫画版を併設し、画像が読み込めない場合も本文を読める構成にする。
- 画像には内容を伝える `alt` を設定し、漫画には短い文字起こしを添える。
- 将来CSSや表示方法を変えても、既存エピソードのURLとファイル名は維持する。
