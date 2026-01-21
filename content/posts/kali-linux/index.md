+++
date = '2025-12-29T00:42:25+09:00'
draft = false
title = 'Kali Linux初期設定'
tags = ['Kali Linux']
+++

## 基本設定

### キーボード設定
キーボードを日本語配列にします。この後の設定でコマンドを実行するためにも、まずはキーボード入力できるようにします。
1. `Keyboard`を開きます。
2. `Use system defaults`をオフにします。
3. `Layout` > `Keyboard layout`で、`English`を`Japanese`にします。

### タイムゾーン設定
1. `Time And Date`を開きます。
2. `Time zone`を`Asia/Tokyo`に。

### パッケージ最新化
ターミナルで、以下のコマンドを入力して実行します。
   ```bash
   sudo apt update && sudo apt full-upgrade -y && sudo apt autoremove -y
   ```

## 任意設定

### rockyou.txt.gzの展開
[wordlists](https://www.kali.org/tools/wordlists/)パッケージの`rockyou.txt`は`gzip`で圧縮されています。  
ワードリストとして使うために、展開しておきます。


ターミナルで、以下のコマンドを入力して実行します。

```bash
sudo gunzip /usr/share/wordlists/rockyou.txt.gz
```

### ターミナル設定

terminatorを使います。

1. ターミナルで、以下のコマンドを入力して実行します。

```
sudo apt install terminator
```

2. Default Applications
- `Utilities` > `Terminal Emulator`で、`Terminator`に。

1. Preferences
- `Global` > `Behavior` > `Window state` > `Maximized`
- `Profiles` > `Background` > `Solid color`
- `Scrolling` > `Infinite Scrollback`

### その他パッケージのインストール

#### peass

https://www.kali.org/tools/peass-ng/

```
sudo apt install peass
```

#### LibreOffice

```
sudo apt install libreoffice
```

#### rlwrap

```
sudo apt install rlwrap
```

#### SecLists

https://www.kali.org/tools/seclists/

```
sudo apt install seclists
```
#### FeroxBuster

https://www.kali.org/tools/feroxbuster/

```
sudo apt install feroxbuster
```

#### Autorecon

https://www.kali.org/tools/autorecon/

```
sudo apt install autorecon
```
