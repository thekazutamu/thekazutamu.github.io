+++
date = '2025-12-29T00:42:25+09:00'
draft = false
title = 'Kali Linux初期設定'
tags = ['Kali Linux']
+++

## キーボード設定
キーボードを日本語配列にします。コマンドを実行するにも、まずは打てるようにします。
1. `Use system defaults`をオフにします。
2. `Layout` > `Keyboard layout`で、`English`を`Japanese`にします。

## タイムゾーン設定
1. `Time And Date`
2. `Time zone`を`Asia/Tokyo`に。

## rockyou.txt.gzの展開
rockyou.txtはgzで圧縮されています。ワードリストとして使うために、展開しておきます。
```bash
sudo gunzip /usr/share/wordlists/rockyou.txt.gz
```