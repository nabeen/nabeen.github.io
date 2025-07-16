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

[^songmu]: [リポジトリの内容を別リポジトリに push する GitHub Action を公開した \| おそらくはそれさえも平凡な日々](https://songmu.jp/riji/entry/2025-06-24-action-push-to-another-repository.html)
[^classmethod]: [GitHub Apps \+ GitHub Actionsで必要なアクセス権限のみ付与した一時的なアクセストークンを発行する \| DevelopersIO](https://dev.classmethod.jp/articles/getting-an-access-token-with-only-the-necessary-permissions-on-github-appsgithub-actions/)