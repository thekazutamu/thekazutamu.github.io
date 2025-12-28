+++
draft = false
date = '2025-12-15T23:27:02+09:00'
lastmod = '2025-12-20T23:27:02+09:00'
title = 'OSCP+合格体験記'
tags = ['OSCP', '資格']
showHero = true
heroStyle = 'background'
+++
今年、OSCP+に合格しました。
私も受験するまでに様々な合格体験記を読みましたが、これから挑戦される方の参考になればと思い、本記事では私なりの視点で得られた知見を共有します。

試験の概要については、[OffSec公式サイト](https://www.offsec.com/courses/pen-200/)で最新の情報をご確認ください。



## 合格までの道のり

2024年6月から、PEN-200を受講しました。
当初は加点10ポイントの取得を目標に、テキストを順調に読み進め、練習問題にも取り組んでいました。

しかし8月、[試験制度の変更に関する通知](https://help.offsec.com/hc/en-us/articles/29840452210580-Changes-to-the-OSCP)を受けたことをきっかけに、学習方針を大きく見直しました。それ以降は、[Tj Null](https://docs.google.com/spreadsheets/u/1/d/1dwSMIAPIam0PuRBkCiDI88pU3yzrqqHkDtBngUHNCw8/htmlview)や[Lainkusanagi](https://docs.google.com/spreadsheets/d/18weuz_Eeynr6sXFQ87Cd5F0slOj9Z6rt/edit?gid=487240997#gid=487240997)を参考に、Proving GroundsやChallenge Labsのマシンを中心として、ほぼ毎日1台のペースで攻略する実践重視の学習に切り替えました。

1年以内に2回受験できる[Learn One](https://www.offsec.com/products/learn-one/)プランを契約していたため、まずは2025年2月に初回受験しました。しかし結果は不合格。ある程度の自信があっただけに、この結果には意気消沈しつつ、自分に何が足りなかったのか自問自答して、その後しばらくはほとんど勉強できない状態が続きました。

そのまま期限が迫り、ほぼ何も知識をアップデートしないまま、同年6月に再受験。結果、無事合格することができました。

## おすすめのサイトや動画

[Juggernaut Pentesting Academy](https://juggernaut-sec.com/)

HackTheBoxのウォークスルーや、Linux/Windowsのハッキング技術について解説。基礎から丁寧に説明されており、初学者が読んでも理解しやすい記事になっている。

[ByteSized Security (YouTube動画)](https://www.youtube.com/@ByteSizedSec/videos)

マシンの実況解説や、使っているツールを紹介してくれている。内容も興味深いですが、チル系の音楽を流しながら着実に攻略を進めていく姿が印象的。リラックスして問題に取り組む姿勢を学びました。

## おすすめのツール

### テキストエディタ 

[Obsidian](https://obsidian.md/)

学んだことは全てObsidianにまとめました。自分の知識量をグラフビューで可視化できるので、モチベーションアップにもつながりました。マイルールとして、全て[MITRE ATT&CK](https://attack.mitre.org/)と関連づけるようにタグ付けしていました。後になって、これはレポート作成に活きると実感しました。

{{< video "obsidian.mp4" >}}

[Sublime Text](https://www.sublimetext.com/)

マシン攻略中、一時的なメモを残すためにSublime Textを使っていました。自分の中でさらに格上げすべきと判断した情報は、[cherrytree](https://www.kali.org/tools/cherrytree/)に書き写しました。

### ターミナル

terminator

必需品です。[tmux](https://www.kali.org/tools/tmux/)はあまり自分とは相性が合いませんでした。

### ブラウザのお気に入り（ブックマーク）

Kali Linuxのブラウザに登録していたブックマークをご紹介します。

[Exploit-DB](https://www.exploit-db.com/)

もちろん[searchsploit](https://www.kali.org/tools/exploitdb/)でも検索できますが、Webブラウザの方が見やすいと感じています。

[Crackstation](https://crackstation.net/)

これが唯一解となることは稀かと思いますが、忘れないために登録しています。

[Reverse Shell Generator](https://www.revshells.com/)

[CyberChef](https://gchq.github.io/CyberChef/)


## さいごに

試験対策を通して[Try Harder](https://www.offsec.com/blog/what-it-means-to-try-harder/)の精神を身につけることができました。OffSec社の意図や目的がそこにあるとすれば、OSCPはその狙いに成功している試験だと感じています。

