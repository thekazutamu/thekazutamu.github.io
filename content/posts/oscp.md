+++
draft = false
title = 'OSCP+合格体験記'
+++
今年、OSCP+に合格しました。
私も受験するまでに様々な合格体験記を読みましたが、これから挑戦される方の参考になればと思い、本記事では私なりの視点で得られた知見を共有します。

試験の概要については、[OffSec公式サイト](https://www.offsec.com/courses/pen-200/)で最新の情報をご確認ください。

## 概要

2025年2月に初めて受験しましたが、不合格の結果に。同年6月に再受験して、無事合格しました。

## 参考にしたサイトや動画

[Juggernaut Pentesting Academy](https://juggernaut-sec.com/)

HackTheBoxのウォークスルーや、Linux/Windowsのハッキング技術について解説。基礎から丁寧に説明されており、初学者が読んでも理解しやすい記事になっている。

[ByteSized Security (YouTube動画)](https://www.youtube.com/@ByteSizedSec/videos)

マシンの実況解説や、使っているツールを紹介してくれている。内容も興味深いですが、チル系の音楽を流しながら着実に攻略を進めていく姿が印象的。リラックスして問題に取り組む姿勢を学びました。

## ツール群

### テキストエディタ

[Obsidian](https://obsidian.md/)

学んだことは全てObsidianにまとめました。自分の知識量をグラフビューで可視化できるので、モチベーションアップにもつながりました。マイルールとして、全てMITRE ATT&CKと関連づけるようにタグ付けしていました。

[Sublime Text](https://www.sublimetext.com/)

マシン攻略中、一時的なメモを残すためにSublime Textを使っていました。自分の中でさらに格上げすべきと判断した情報は、cherrytreeに書き写しました。

### ターミナル

terminator

必需品です。tmuxはあまり自分とは相性が合いませんでした。

### ブラウザのお気に入り（ブックマーク）

[Exploit-DB](https://www.exploit-db.com/)

[Reverse Shell Generator](https://www.revshells.com/)

[Crackstation](https://crackstation.net/)

[CyberChef](https://gchq.github.io/CyberChef/)

### スキャン

[FeroxBuster](https://www.kali.org/tools/feroxbuster/)

[Autorecon](https://www.kali.org/tools/autorecon/)

[Rustscan](https://github.com/bee-san/RustScan)

[SecLists](https://www.kali.org/tools/seclists/)