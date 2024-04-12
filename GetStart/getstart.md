# 1. 使い方ガイド

# 2. 目次

- [1. 使い方ガイド](#1-使い方ガイド)
- [2. 目次](#2-目次)
- [3. Linuxコマンド入門](#3-linuxコマンド入門)
  - [3.1. ファイル操作](#31-ファイル操作)
    - [3.1.1. ネットワーク](#311-ネットワーク)
    - [3.1.2. テキスト操作](#312-テキスト操作)
- [4. 便利なコマンド集](#4-便利なコマンド集)
  - [4.1. ls](#41-ls)
  - [4.2. ip](#42-ip)
- [5. 参考資料](#5-参考資料)

# 3. Linuxコマンド入門

## 3.1. ファイル操作
| コマンド | 操作の説明 |
| ------- | -------- |
| cd | 指定したディレクトリへ移動します |
| ls | 対象ディレクトリの情報を表示します |
| pwd | 現在アクセスしているディレクトリを表示します |
| mkdir | 新しいディレクトリを作成します |
| cp | 対象のファイルをコピーします |
| touch | ファイルを新規作成、またはタイムスタンプを変更します |
| rm | 指定したファイルを削除します |
| mv | ファイルの移動や名称変更などを行います |
| cat | テキストファイルの内容を表示します |
| chmod | 指定したファイルやフォルダの権限を変更します |
| chown | 指定したファイルやフォルダの所有者情報を変更します |
| tar | 複数ファイルを圧縮して一つにまとめる、または圧縮されたファイルの展開を行います |
| find | 対象ファイルを検索します |

### 3.1.1. ネットワーク
| コマンド | 操作の説明 |
| ------- | -------- |
| ip | ネットワークデバイスやルーティング、ポリシーなどの表示と変更を行うコマンド |
| ping | ネットワーク疎通を確認します |
| hostname | ホスト名を表確認します |
| nslookup | DNSによる名前解決を行います |
| ssh | リモートログイン(物理的に離れたコンピュータへネットワークを利用して接続)するコマンドです |
| ftp | ファイルのFTP転送を行います |

### 3.1.2. テキスト操作
| コマンド | 操作の説明 |
| ------- | -------- |
| cut | 文字を切り出して表示します |
| grep | ファイル内に含まれる文字列を検索します |
| head | ファイル内容を先頭から10行まで表示します |
| less | ファイル内容をスクロール操作で表示します |
| more | ファイルの内容をページごとに表示します |
| vi | テキストエディタの起動や編集を行います |

# 4. 便利なコマンド集

## 4.1. ls

```bash
ls -a 
ls -l
```
| オプション | 出力されるもの |
| -- | -- |
| -a | .(ドット)で始まるファイルも含めて表示する |
| -l | ファイルの詳細情報を表示する |

```bash
nuskrbb@fedora:~$ ls -a
.              .bash_profile  .cert    Documents   .gitignore  .mozilla    .pki       .themes  .wget-hsts                 .zcompdump-NuskWindows-5.9      .zshrc.pre-oh-my-zsh
..             .bashrc        .config  .dotnet     .gnome      Music       Public     .var     .z                         .zcompdump-NuskWindows-5.9.zwc
.bash_history  .cache         Desktop  Downloads   .local      .oh-my-zsh  .ssh       Videos   .zcompdump-fedora-5.9      .zsh_history
.bash_logout   .cargo         Develop  .gitconfig  MEGA        Pictures    Templates  .vscode  .zcompdump-fedora-5.9.zwc  .zshrc
nuskrbb@fedora:~$ ls -l
total 0
drwxr-xr-x. 1 nuskrbb nuskrbb  158 Apr  8 22:39 Desktop
drwxr-xr-x. 1 nuskrbb nuskrbb   72 Apr 10 16:02 Develop
drwxr-xr-x. 1 nuskrbb nuskrbb   38 Apr 10 16:02 Documents
drwxr-xr-x. 1 nuskrbb nuskrbb  826 Apr  9 23:03 Downloads
drwxr-xr-x. 1 nuskrbb nuskrbb 1240 Apr  9 08:50 MEGA
drwxr-xr-x. 1 nuskrbb nuskrbb    0 Apr  8 13:44 Music
drwxr-xr-x. 1 nuskrbb nuskrbb   62 Apr  8 23:54 Pictures
drwxr-xr-x. 1 nuskrbb nuskrbb    0 Apr  8 13:44 Public
drwxr-xr-x. 1 nuskrbb nuskrbb    0 Apr  8 13:44 Templates
drwxr-xr-x. 1 nuskrbb nuskrbb   32 Apr  8 14:35 Videos
```

## 4.2. ip
```bash
ip a
ip link
```

| オブジェクト | 出力されるもの |
| -- | -- |
| addr または a | ネットワークデバイスのIPアドレス |
| link | ネットワークデバイス |

```bash
nuskrbb@fedora:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever
2: enp61s0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc mq state DOWN group default qlen 1000
    link/ether b0:25:aa:51:6f:e1 brd ff:ff:ff:ff:ff:ff
3: wlo1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
    link/ether 38:7a:0e:f5:8b:56 brd ff:ff:ff:ff:ff:ff
    altname wlp0s20f3
    inet 172.27.126.188/16 brd 172.27.255.255 scope global dynamic noprefixroute wlo1
       valid_lft 3834sec preferred_lft 3834sec
    inet6 fe80::77b5:1c16:f01e:20a2/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
nuskrbb@fedora:~$ ip link
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: enp61s0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc mq state DOWN mode DEFAULT group default qlen 1000
    link/ether b0:25:aa:51:6f:e1 brd ff:ff:ff:ff:ff:ff
3: wlo1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP mode DORMANT group default qlen 1000
    link/ether 38:7a:0e:f5:8b:56 brd ff:ff:ff:ff:ff:ff
    altname wlp0s20f3

```

# 5. 参考資料
* https://udemy.benesse.co.jp/development/system/linux-command.html
* https://linuxfan.info/ls