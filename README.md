# 昭和プロンプト劇場 AI部下とポンコツ上司

> 昭和の勢いを、令和の仕様書に変換せよ。

笑いあり、涙ありのハートフルAIコメディです。

会社から業務効率化のためにAI部下を与えられたポンコツ上司が、曖昧な指示で衝突しながらも、少しずつ「AIへの指示の出し方」を覚えていきます。やがて二人は、単なる上司と道具ではなく、互いの意図を理解する相棒へと近づいていきます。

**この物語はフィクション？です。**

## 現在の状態

作品設定と公開サイトに加え、第1話「新人AI、配属される」を収録しています。

## フォルダ構成

```text
showa-prompt-theater/
├─ README.md                 作品概要と運用案内
├─ settings/                 作品全体の設定と執筆ルール
├─ characters/               キャラクター設定
├─ episodes_md/              本編原稿（Markdown）
├─ prompts/                  「今日の昭和プロンプト」の台帳
├─ glossary/                 用語解説の台帳
└─ docs/                     GitHub Pages用の静的サイト
   └─ episodes/              公開用エピソードHTML
```

## 運用方法

1. 執筆前に `settings/` と `characters/` を確認します。
2. 本編原稿は `episodes_md/epXXX_slug.md` として追加します。
3. 各話で扱ったプロンプトと用語を、それぞれの台帳にも追記します。
4. 公開用HTMLは `docs/episodes/epXXX.html` として追加します。
5. `docs/index.html` に新しい話へのリンクを追加します。
6. 実在サービス名、規約回避につながる説明、危険な自動化手順は書きません。必要な題材はフィクションとして抽象化します。

ファイル名の `XXX` は `001` から始まる3桁の連番を使用します。公開前には、6ページ構成、スマホでの読みやすさ、キャラクターの口調、注意事項を確認してください。

## エピソードを追加する方法

各話は、原稿、公開ページ、学習資料の順に追加します。第1話では次のファイル名を使用しています。

1. `episodes_md/README.md` のテンプレートを使い、`episodes_md/ep001_shinjin_ai_haizoku.md` を作成します。
2. 1ページ目をタイトルページ、2ページ目から5ページ目を「起・承・転・結」、6ページ目を学びのページとして執筆します。
3. 第1話で使ったプロンプトを `prompts/showa_prompts.md` に追記します。
4. 初登場の用語を `glossary/terms.md` に追記します。
5. `docs/episodes/ep001.html` を作成し、共通CSSとして `../style.css` を読み込みます。
6. タイトルページには `.episode-page.title-page`、本文4ページには `.episode-page.story-page`、学びのページには `.episode-page.learning-page.prompt-page` を指定します。
7. 6ページ全体を `.episode-reader.page-track` で囲みます。
8. `docs/index.html` のエピソード欄に、第1話のタイトルと `episodes/ep001.html` へのリンクを追加します。
9. `docs/prompts.html` と `docs/glossary.html` に、第1話で追加した内容を掲載します。
10. 公開前に、リンク切れ、縦書き表示、スマホ幅での横送り、各ページの見切れ、6ページ目の横書きを確認します。

原稿と公開HTMLは同じ話数を使用します。公開後に本文を直した場合は、Markdown原稿とHTMLの両方を更新し、内容が食い違わないようにします。

## 将来の拡張

### キャラクター画像

- 画像は `docs/assets/images/characters/` にまとめます。
- ファイル名は `ponkotsu-joshi.webp`、`ai-buka.webp` のように、半角英数字とハイフンを使用します。
- `docs/characters.html` の `.character-visual` 内へ `<img>` を追加します。
- 画像には人物名や場面が分かる `alt` を必ず設定します。
- WebPを基本とし、必要に応じてPNGを使用します。スマホ表示を重くしないサイズへ圧縮します。

### エピソード挿絵

- 画像は `docs/assets/images/episodes/ep001/` のように話数別で管理します。
- 挿絵は `.episode-illustration` を使用し、本文を読む順序を邪魔しない位置へ置きます。
- 画像がなくても物語を読める状態を保ちます。

### 4コマ漫画版

- 文章版を置き換えず、同じ話数ページ内に別セクションとして追加します。
- 4コマ全体を1枚にする場合は `.comic-panel` を使用します。
- コマを分割する場合は、上から下へ読めるHTML順で並べます。
- ページ上部に「文章版」「4コマ版」へのページ内リンクを設けます。
- 漫画のせりふや内容を、画像の代替テキストまたは短い文字起こしでも提供します。

### サイト規模が大きくなった場合

- 話数一覧が増えたら `docs/episodes/index.html` を追加し、トップページには最新話だけを表示します。
- 画像用CSSは `docs/style.css` に追加し、既存の `.episode-page` などの名前を変更しないようにします。
- JavaScriptを導入する場合も、本文と基本ナビゲーションはJavaScriptなしで利用できる状態を保ちます。
- 作品設定の正本は `settings/` と `characters/`、本文の正本は `episodes_md/` とし、`docs/` は公開用として扱います。

## 公開方針

`docs/` は外部ライブラリを使わないHTML/CSSだけの構成です。GitHub Pagesのブランチ公開機能から、そのまま公開できます。

1. GitHubへリポジトリを作成して、既定ブランチへプッシュします。
2. GitHubの `Settings` → `Pages` を開きます。
3. `Build and deployment` の `Source` で `Deploy from a branch` を選びます。
4. ブランチに `main`、フォルダに `/docs` を指定して保存します。
5. `Settings` → `Pages` に表示されたURLへアクセスします。
