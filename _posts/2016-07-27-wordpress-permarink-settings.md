---
title: WordPress パーマリンク設定で404エラー
date: 2016-07-27 00:08:08
categories:
- Engineering
tags:
- WordPress
- apache
---

パーマリンク設定を変更すると，投稿ページなどが404エラーに．

httpd.confと.htaccessファイルを作成して解決する

### 設定環境

* CentOS 6
* Apache2.2

### httpd.confを書き換えて，mod_rewriteを有効にする

#### SuperUser権限でhttpd.confを開く

`# vim /etc/httpd/conf/httpd.conf`
317行目あたりのDirectoryディレクティブ
`Directory "/var/www/html"`
の中の
`AllowOverride None`
を
`AllowOverride All`
に変更する

### .htaccessファイルを作成する

#### WordPressがインストールされているディレクトリ内に.htaccessファイルを作成する

筆者の場合は
`/var/www/html/`
をWordPressがインストールされているルートディレクトリとして設定している
`cd /var/www/html/`

#### .htaccessファイルを作成する

`/var/www/html`内で
`# vim .htaccess`
を記述

### httpd再起動` # service httpd restart`

で完了.

> 参考文献
> [WordPressのパーマリンクが表示されないときの解決法(ubuntu ×　apache2)](http://qiita.com/hyperkinoko/items/de018714c95e675fd5f9)
> [WordPressのパーマリンク変更でNot Foundの対処法](http://www.eastforest.jp/esthome/wordpress/3279)