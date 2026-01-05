---
title: ブログのテーマを github-style から dream に変更した
slug: update-blog-theme
summary:
date: 2026-01-05
lastmod:
draft: true
author: nabeen
avatar: /images/avatar.png
nolastmod: true
categories:
  - tech
tags:
  - Hugo
---
このブログは今現在 Hugo で運用しているが、そのテーマを変更した。エコシステムがしっかりしていると、テーマも豊富にあるので体験が良い。

## Before

Github Style[^github-style] を使っていた。理由としては、GitHub 好きだし、ブログもそれに近いデザインだったらなんかテンション上がるかな、というもの。確かに草も生やせるので、テンションは上がったが、別にだからといってブログを書くようになった、わけではなかった。

で、今年はブログをちゃんと書いていこう、というか駄文でもいいのでアウトプットをしっかりしていこうという抱負を立てているので、もうちょっとライトに書いても違和感のないデザインのものが欲しかった。

## After

そこで色々探してみた結果たどり着いたのが、今使っている Dream[^dream] というテーマ。ZEN モードというのがあって、THE シンプルな感じがよかった。

## 変更が必要だった部分
```toml

[module]
[[module.mounts]]
source = 'content/post'
target = 'content/posts'
```

[^github-style]: [Github Style](https://themes.gohugo.io/themes/github-style/)
[^dream]: [Dream](https://themes.gohugo.io/themes/hugo-theme-dream/)