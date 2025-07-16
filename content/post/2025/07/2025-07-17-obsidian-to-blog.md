---
title: Obsidianで執筆する環境を整えた
slug: obsidian-to-blog
summary: 無事に構築できた。執筆量が増えるかどうかはわからない
date: 2025-07-17
draft: true
authors:
  - nabeen
categories: 
tags:
---
やる気がまだあるうちに、ざっと組み上げた。これで今後ブログを書くハードルがグッと下がったはず。

## 仕組み

Obsidian 側に、Hugo の content にまるっと投げられるようなディレクトリ構成を作って、記事 [^songmu] の通りの GitHub Actions を組んだ。

GitHub App の設定については、DeveloperIO[^classmethod] の記事を参考にした。

具体的には、Obsidian 側に Blog というディレクトリを掘って、content 配下をまるっとブログを管理しているリポジトリに sync している。

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

## 執筆フロー

[^songmu]: [リポジトリの内容を別リポジトリに push する GitHub Action を公開した \| おそらくはそれさえも平凡な日々](https://songmu.jp/riji/entry/2025-06-24-action-push-to-another-repository.html)
[^classmethod]: [GitHub Apps \+ GitHub Actionsで必要なアクセス権限のみ付与した一時的なアクセストークンを発行する \| DevelopersIO](https://dev.classmethod.jp/articles/getting-an-access-token-with-only-the-necessary-permissions-on-github-appsgithub-actions/)