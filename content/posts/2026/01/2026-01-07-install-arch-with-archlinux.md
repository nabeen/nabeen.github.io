---
title: ParrotOS から Arch Linux に乗り換えた
slug: install-arch-with-archlinux
summary:
date: 2026-01-07
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
Arch Linux をインストールしたのでやったことをメモしておく。

といっても、自分でなにか調べてということはないので、参考にしたリンク集、という感じにはなるが。

## 事前準備

まず、何はともあれ、ISO を落としていく。適当なミラーから落とせばいい。僕はやっぱ JAIST じゃね？と思ったので、JAIST にしたが、本当にどこでもお好きなところからどうぞ。

あとは Rufus でポチポチしながら焼けばよい。

## インストール&日本語化

これまで Linux をインストールするときは、使っている PC との相性をみたい（主にドライバがちゃんと動くのかとか）ので、Live USB で起動して、一通り触ってみてからインストールしていたが、Arch Linux は初期は GUI がないのでぶっつけ本番でインストールした。

`archinstall` が付随しているので、それを使う。さすがに Linux 初心者が、参考記事や wiki が世の中に溢れているとはいえ、CLI を使ってもろもろの設定をしてもうまく起動しない未来しかみえないので、こういうのは非常にありがたい。

ただ設定値とかもよくわからないものが多いので、いい感じの設定 [^archinstall] を参考にしながら進めた。

Wi-Fi が一番の心配点ではあったが、特にトラブルもなく接続できた。あとは日本語化 [^japanese] の設定だけして一旦終わり。日本語化といいつつも、OS の設定自体は英語のままで、日本語フォントとか、日本語キーボードの設定、IME の設定とかそのあたりをやった。

あとはいつも使っている Obsidian、Todoist を入れたり、AUR 用に `yay` を入れたり。まぁここまで来たら、他には特に難しいところはないし、多分いくらでもリカバリ可能なはず。

## やりたいこと

挙げればキリがないので、おもいつくｍ

[^archinstall]: [archinstallを使って簡単にArch Linuxをインストール【KDE Plasma】 #初心者 - Qiita](https://qiita.com/poyotanp/items/cc1ea62f4c61e15f03a4)
[^japanese]: [Arch Linuxの初期設定（日本語化、日本語入力）【KDE Plasma】 #archLinux - Qiita](https://qiita.com/poyotanp/items/e59336dd6b42283fda2e)