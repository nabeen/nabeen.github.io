---
title: Obsidianで執筆する環境を整えた
slug: obsidian-to-blog
summary: 無事に構築できた。執筆量が増えるかどうかはわからない
date: 2025-07-16
draft: false
author: nabeen
avatar: /images/avatar.png
nolastmod: true
categories: poem
tags:
  - Obsidian
---
やる気がまだあるうちに、ざっと組み上げた。これで今後ブログを書くハードルがグッと下がったはず。

## 仕組み

Obsidian 側に、Hugo の content にまるっと投げられるようなディレクトリ構成を作って、記事 [^songmu] の通りの GitHub Actions を組んだ。

GitHub App の設定については、DeveloperIO[^classmethod] の記事を参考にした。

具体的には、Obsidian 側に Blog というディレクトリを掘って、content 配下をまるっとブログを管理しているリポジトリに sync している。月毎にディレクトリを切っているのは、管理上の好み。

```bash
$ tree ./Blog 
./Blog
└── content
    └── post
        └── 2025
            └── 07
                ├── 2025-07-15-create-new-blog.md
                └── 2025-07-17-obsidian-to-blog.md
```

GitHub Actions はこんな感じで組んである。

```yml
name: push to blog
on:
  push:
    branches: [main]
    paths:
    - 'Blog/content/**'
jobs:
  push:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v4
    - id: generate_token
      uses: actions/create-github-app-token@v1
      with:
        app-id: ${{ secrets.APP_ID }}
        private-key: ${{ secrets.APP_PRIVATE_KEY }}
        repositories: nabeen.github.io
    - uses: Songmu/action-push-to-another-repository@v2
      with:
        token: ${{ steps.generate_token.outputs.token }}
        source-directory: Blog/content
        destination-repository: nabeen/nabeen.github.io
        destination-directory: content
```

Obsidian の Git プラグインを入れて自動 commit/push をするようにしているので、特に GitHub 上でなにかやる必要もない。便利。

## 執筆フロー

普段 Obsidian でデイリーノートを中心に RSS を消化したり、ちょっと考え事したりとか、読書メモを書いたりしている。なので、その中で、あ、これ記事にまとめてもいいかも、と思ったその瞬間に、記事を書き始めることができる。

何かをやるときに、それをやるためのハードルが低いってのは、これまでの経験上めちゃくちゃ重要なので、思っていた感じのものが構築できてうれしい。

じゃあ毎日書くかというと、それはわからないけど。

アウトプットを狙っている、というよりは、アウトプット用に推敲しているなかで、自分の中でも言語化の質が自然と高まっていく、みたいな状態を目指しているので、無理に毎日書きたいわけでもない。

ニュースレター的に週に 1 回くらいが無理なく書けるかもなぁという気もしている。

今後に期待してほしい。

[^songmu]: [リポジトリの内容を別リポジトリに push する GitHub Action を公開した \| おそらくはそれさえも平凡な日々](https://songmu.jp/riji/entry/2025-06-24-action-push-to-another-repository.html)
[^classmethod]: [GitHub Apps \+ GitHub Actionsで必要なアクセス権限のみ付与した一時的なアクセストークンを発行する \| DevelopersIO](https://dev.classmethod.jp/articles/getting-an-access-token-with-only-the-necessary-permissions-on-github-appsgithub-actions/)