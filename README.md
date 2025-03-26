# agri-iot-blog

サイト: https://tcloud-farm.github.io/agri-iot-blog/

## 概要
GitHub Pagesを利用して、農業IoTプロジェクトの進捗をお伝えするブログです。

## 記事の更新方法
1. `_posts`フォルダに新しいMarkdownファイルを作成します。
   - ファイル名は、`YYYY-MM-DD-記事タイトル.md`の形式で作成してください。
   - 例: `2025-03-26-project-started.md`
   - ファイル名は、英数字とハイフンのみ使用してください。
   - ファイル名は、記事のタイトルを反映させてください。
2. 新しいMarkdownファイルに、以下のようなFront Matterを追加します。
```yaml
---
layout: post
title:  "農業IoTプロジェクトのブログ、始めます！"
date:   2025-03-26 14:50:11 +0900
background: '/assets/images/20250326-bg.svg'
author:  "たなべ"
---
```
- `layout`は`post`を指定してください。
- `title`は記事のタイトルを指定してください。
- `date`は記事の投稿日を指定してください。フォーマットは`YYYY-MM-DD HH:MM:SS +0900`です。
- `background`は記事の背景画像を指定してください。画像は`/assets/images/`フォルダに保存してください。
  - 背景の画像名は `YYYYMMDD-bg.jpg|png|svg` の形式で保存してください。
  - 例: `20250326-bg.svg`
- `author`は記事の著者名を指定してください。 
- `categories`は記事のカテゴリを指定してください。複数指定する場合は、カンマ区切りで指定してください。
  - 例: `News, Hardware, Software`

3. 記事の内容をMarkdown形式で記述します。
- 画像を入れたい場合は `/assets/images/`フォルダに保存し、以下のように記述します。
    - 画像のクラスは、Bootstrapの`img-fluid`を指定しています。これにより、レスポンシブデザインが適用されます。
```markdown
<img class="img-fluid" src="/agri-iot-blog/assets/images/20250326-03.jpg"/>
```

4. 記事を保存し、localでビルドをします。
```shell
$ bundle exec jekyll clean
$ bundle exec jekyll build
```
- RubyとBundlerがインストールされている必要があります。
  - `bundle exec jekyll build`を実行すると、`docs`フォルダにビルドされたHTMLファイルが生成されます。


## 公開方法

localビルド後にGitHubにpushすることで、GitHub Pagesに公開されます。
```shell
$ git add .
$ git commit -m "ここにはコミットメッセージを入れます"
$ git push origin main
```