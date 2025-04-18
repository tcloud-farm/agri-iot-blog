# agri-iot-blog

サイト: https://tcloud-farm.github.io/agri-iot-blog/

## 概要
GitHub Pagesを利用して、農業IoTプロジェクトの進捗をお伝えするブログです。

## 記事の更新手順概要
1. 公開する日付のブランチを作成します。
   - 例: `20250326`
   - ブランチ名は、`YYYYMMDD`の形式で作成してください。
   - 例: `20250326`
   - ブランチ名は、英数字のみ使用してください。
2. `_posts`フォルダに新しいMarkdownファイルを作成します。
   - 作成のルールは、下記の「記事の作成手順」を参照してください。
3. （オプション）localのRuby環境でJekyllでビルドして、表示を確認します。
    ```shell
    $ bundle exec jekyll serve
    ```
4. GitHubでプルリクエストを作成します。
   - 実際の公開は、プルリクエストをレビュー後に田名辺がマージを行うことで公開されます。
   
## 記事の作成手順
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

4. 記事を保存し、localでビルドをします。（localでのビルド方法は後述します）
```shell
$ bundle exec jekyll clean
$ bundle exec jekyll build
```
- RubyとBundlerがインストールされている必要があります。
  - `bundle exec jekyll build`を実行すると、`docs`フォルダにビルドされたHTMLファイルが生成されます。このdocsフォルダが最終的に公開されるページです。


## （参考）公開方法

localビルド後にGitHubにpushすることで、GitHub Pagesに公開されます。
```shell
$ git add .
$ git commit -m "ここにはコミットメッセージを入れます"
$ git push origin main
```


## 参考
### Jekyllについて
- [Jekyll公式サイト](https://jekyllrb.com/)

Jekyllは、Rubyで書かれた静的サイトジェネレーターです。GitHub PagesはJekyllを利用して、静的なWebサイトを簡単にホスティングすることができます。
- [GitHub Pages](https://pages.github.com/)

### localでの環境構築について
RubyとBundlerがインストールされている必要があります。
- [Rubyのインストール](https://www.ruby-lang.org/ja/documentation/installation/)

Ruby本体は、[rbenv](https://github.com/rbenv/rbenv) や [RVM](https://rvm.io/)、[asdf](https://asdf-vm.com/) を使ってインストールすることもできます。
Bundlerは、Rubyのパッケージ管理ツールです。Gemfileに記載された依存関係を解決し、必要なGemをインストールします。
```shell
$ gem install bundler
```

localでのビルドには、以下のコマンドを実行します。
```shell
$ bundle install
$ bundle exec jekyll serve
```

- `bundle install`を実行すると、Gemfileに記載された依存関係を解決し、必要なGemをインストールします。これは基本的に一度だけ行えば大丈夫です。
- `bundle exec jekyll serve`を実行すると、Jekyllがローカルサーバーを起動し、`http://localhost:4000`でサイトを確認することができます。ローカルサーバーは、ファイルの変更を監視して自動的に再ビルドします。
- `bundle exec jekyll build`を実行すると、Jekyllが静的なHTMLファイルを生成します。これにより、GitHub Pagesにpushする準備が整います。
- `bundle exec jekyll clean`を実行すると、ビルドされたファイルを削除します。これにより、クリーンな状態でビルドを行うことができます。

GitHub Pagesにpushする前に、ローカルでビルドしたHTMLファイルを確認することができます。ローカルサーバーを起動して、 [http://localhost:4000/agri-iot-blog/](http://localhost:4000/agri-iot-blog/) にアクセスしてください。