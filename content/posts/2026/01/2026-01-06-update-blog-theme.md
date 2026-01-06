---
title: ブログのテーマを github-style から dream に変更した
slug: update-blog-theme
summary:
date: 2026-01-05
lastmod:
draft: false
author: nabeen
avatar: /images/avatar.png
nolastmod: true
categories:
  - tech
tags:
  - Hugo
---
このブログは今現在 Hugo で運用しているが、そのテーマを変更した。ブログを書き始めるには、まずこういうところから整えていくタイプである。

Hugo はエコシステムがしっかりしており、テーマが豊富にあるのでこうサクッと差し替えができるのは非常に体験が良い。テーマを作るのは...テンプレートエンジンなので、ちょっと体験は良くないが。

## Before

Github Style[^github-style] を使っていた。理由としては、GitHub 好きだし、ブログもそれに近いデザインだったらなんかテンション上がるかな、という単純なもの。草も生やせるので、テンションは確かに上がったが、別にだからといってブログを書くようになった、わけではなかった。

で、今年はブログをちゃんと書いていこう、というか駄文でもいいのでアウトプットをしっかりしていこうという抱負を立てているので、もうちょっとライトに書いても違和感のないデザインのものが欲しかった。

## After

そこで色々探してみた結果たどり着いたのが、今使っている Dream[^dream] というテーマ。ZEN モードというのがあって、THE シンプルな感じがよかった。

ドキュメントもしっかりしているので、導入で迷う部分はほぼないと思う。ヘッダーやフッターなどの最低限のカスタマイズはできるし、うまく動かない部分もソースを読めばだいたいなんとかなる（なんとかなった）。

## 変更が必要だった部分

前に使っていたテーマの記事置き場が `post` で、それが Dream と合わなかったので、以下の設定をして逃した。

```toml
[module]
[[module.mounts]]
source = 'content/post'
target = 'content/posts'

[[module.mounts]]
source = 'content/about'
target = 'content/about'

[[module.mounts]]
source = 'content/search'
target = 'content/search'
```

別にこのタイミングで変えてもよかったのだけど Obsidian のリポジトリのコピーを Hugo のリポジトリに送っているとかいうちょっと面倒くさいことをしていて、そのへんを書き換えるのがやや億劫だったので、既存のつくりのまま使えるようにこの設定を入れた。

複雑なことをしないのであれば、`contentDir`[^contentDir] で変更できるのだけど、今回みたいにやや複雑だと

> For a more flexible approach to configuring this directory, consult the section on module mounts.

ということで、Mounts[^mounts] という機能を使えば実現できる。ちなみにこの機能は今回初めて知った。世の中知らないことばかりである。

## おわりに

とりあえず今のところ結構いい感じだなと思っているので、日々たゆまぬ努力で駄文を錬成していきたい。

[^github-style]: [Github Style](https://themes.gohugo.io/themes/github-style/)
[^dream]: [Dream](https://themes.gohugo.io/themes/hugo-theme-dream/)
[^contentDir]: [All settings](https://gohugo.io/configuration/all/#contentdir)
[^mounts]: [Configure modules](https://gohugo.io/configuration/module/#mounts)