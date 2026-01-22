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

今回、プライベートで Linux をガシガシ使っていくにあたって、このあたりを色々整備しているという話。

## やったもの

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
├── hypr
│   └── .config
│       └── hypr
│           └── hyprland.conf
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
├── waybar
│   └── .config
│       └── waybar
│           ├── config
│           └── style.css
├── yay
│   └── .config
│       └── yay
│           └── config.json
└── zsh
    └── .zshrc

30 directories, 28 files
```
