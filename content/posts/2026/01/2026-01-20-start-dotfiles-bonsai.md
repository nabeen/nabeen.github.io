---
title: dotfiles 盆栽を始めた
slug: start-dotfiles-bonsai
summary:
date: 2026-01-23
lastmod:
draft: true
author: nabeen
avatar: /images/avatar.png
nolastmod: true
categories:
  - tech
tags:
  - dotfiles
---
そろそろちゃんと管理していくか、という気持ちが高まってきたので、最近 dotfiles 盆栽を新しい趣味として始めた。

過去、dotfiles を育てていこうというタイミングがなかったわけではないのだけど、その時は育てるという感覚はあまりなく、適当にバックアップをとっていた感じで終わっていた。それ以来、ターミナルに常駐して仕事するってことが結構減ったので、放置していた。

が、今回、プライベートで Linux をガシガシ使っていくにあたって、このあたりを色々整備している。やっぱりプレーンテキストで設定ファイルが存在するっていうのは、気持ちいいものだ。

最近毎日何かしら触っている。

## やったもの

とりあえず現時点のものを吐き出すと、こんな感じになっている。

```bash
❯ tree ./ -a -I .git
./
├── bin
├── codex
│   ├── .codex
│   │   └── AGENT.md
│   └── skills
├── ghostty
│   └── .config
│       └── ghostty
│           └── config
├── git
│   └── .gitconfig
├── nvim
│   └── .config
│       └── nvim
│           ├── .gitignore
│           ├── init.lua
│           ├── lazy-lock.json
│           ├── lazyvim.json
│           ├── LICENSE
│           ├── lua
│           │   ├── config
│           │   │   ├── autocmds.lua
│           │   │   ├── keymaps.lua
│           │   │   ├── lazy.lua
│           │   │   └── options.lua
│           │   └── plugins
│           │       ├── example.lua
│           │       └── snacks.lua
│           ├── .neoconf.json
│           ├── README.md
│           └── stylua.toml
├── pkglist
│   ├── aur.txt
│   ├── pacman.txt
│   └── README.md
├── README.md
├── sheldon
│   └── .config
│       └── sheldon
│           └── plugins.toml
├── tmux
│   └── .tmux.conf
├── yay
│   └── .config
│       └── yay
│           └── config.json
└── zsh
    └── .zshrc

30 directories, 28 files
```

みての通りだが、`sheldon`[^sheldon] で管理する形をとっている。他にもいくつかあったのは調べた（もう忘れた）が、シンプルに使えそうだったので。まぁ実体が管理されていれば差し替えるのはいつでもできる。

## あきらめたもの

Vim（NeoVim）の設定はかなり時間がかかりそうだったので、諦めてしまった。LazyVim[^lazyvim] でいいかとなり、とりあえず LazyVim を使ってセットアップした。

## これから

タイル型に一種の憧れがあるので、hyprland あたりを試していこうと思っている。実際ちょっと試してみたのだけど、

[^sheldon]: [GitHub - rossmacarthur/sheldon: :bowtie: Fast, configurable, shell plugin manager](https://github.com/rossmacarthur/sheldon)
[^lazyvim]: [GitHub - LazyVim/LazyVim: Neovim config for the lazy](https://github.com/LazyVim/LazyVim)