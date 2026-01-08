---
title: ParrotOS から Arch Linux に乗り換えた
slug: install-arch-with-archlinux
summary:
date: 2026-01-07
lastmod:
draft: false
author: nabeen
avatar: /images/avatar.png
nolastmod: true
categories:
  - tech
tags:
  - ArchLinux
---
Arch Linux をインストールしたのでやったことをメモしておく。

といっても、自分でなにか調べてということはないので、参考にしたリンク集、という感じにはなるが。

## 事前準備

まず、何はともあれ `.iso` を落としていく。適当なミラーから落とせばいい。僕はやっぱり JAIST が好きなので JAIST にしたが、本当にどこでもお好きなところからどうぞ。

あとは Rufus でポチポチしながら焼けばよい。僕は別途 windows マシンを持っているので、windows で焼いた。

## インストール&日本語化

これまで Linux をインストールするときは、使っている PC との相性を調べたい（主にドライバがちゃんと動くのかとか）ので、Live USB で起動して、一通り触ってみてからインストールしていたが、Arch Linux は初期は GUI がないのでぶっつけ本番でインストールした。

インストールは `archinstall` が付随しているので、それを使う。さすがに Linux 初心者が、参考記事や wiki が世の中に溢れているとはいえ、cli を使ってもろもろの設定をしてもうまく起動しない未来しかみえないので、こういうのは非常にありがたい。`archinstall` を使うんだったら別に無理に Arch Linux を使わなくても派生の GUI 付きの OS でもいいのでは？と思われるかもしれない。

言いたいことは非常によくわかるが、僕は原理主義者なので、なるべく素の状態のものを使いたいのだ。

ただ `archinstall` を使ったとしても、よくわからない設定項目も多い。なのでそこはいい感じの設定 [^archinstall] を参考にしながら進めた。まぁこれを見ても、バージョンの違いもあって載ってない設定もいくつかあったわけだけど、ノリで設定して無事にインストール完了。

Wi-Fi が繋がらないと詰むのでここが一番の心配点ではあったが、特にトラブルもなく接続することができた。Blue Tooth も普通に動く。今となってはビビって損した気持ちが強い。

あとは日本語化 [^japanese] の設定だけして一旦終わりとした。日本語化といいつつも OS の設定自体は英語のまま（下手に日本語化するよりも英語のほうが扱いやすい）で、日本語フォントやら日本語キーボードやらの設定と IME の設定など、そのあたりのところまで終わらせた。

なので普通にネットサーフィンするマシンとしても困らない状態にはなった。続きはボチボチやっていこうと思っている。

## 追加インストールしたもの

快適に使うために、いつも使っているアプリである Obsidian、Todoist を入れたり、AUR 用に `yay` を入れたりした。まぁここまで来たら、他には特に難しいところはないし、多分いくらでもリカバリ可能なはず。

あとランチャーも一応入れたな。Reddit で見つけた Vicinae[^vicinae] というやつで、Raycast Inspired と書いてあったので、普段の仕事の開発マシンとの見た目の差分も少なくてよいかなと思ったので。まぁ乗り換えたければあとで乗り換えるということで。

## やりたいこと

挙げればキリがないので、思いつくものだけ

- 指紋認証
- デスクトップのカスタマイズ
- NeoVim のカスタマイズ

...意外と思いつくものが少なかった。とりあえず今年は Linux と仲良くなる年だと思っているので、ゆっくり遊んでいこうと思う。キーボードショートカットはもっといい感じにしたいよなぁとは思う。

[^archinstall]: [archinstallを使って簡単にArch Linuxをインストール【KDE Plasma】 #初心者 - Qiita](https://qiita.com/poyotanp/items/cc1ea62f4c61e15f03a4)
[^japanese]: [Arch Linuxの初期設定（日本語化、日本語入力）【KDE Plasma】 #archLinux - Qiita](https://qiita.com/poyotanp/items/e59336dd6b42283fda2e)
[^vicinae]: [GitHub - vicinaehq/vicinae: A focused launcher for your desktop — native, fast, extensible](https://github.com/vicinaehq/vicinae)