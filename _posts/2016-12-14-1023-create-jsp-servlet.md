---
title: IntelliJでJSP/Servlet環境の構築 mac OS
date: 2016-12-14 10:23:08
categories:
- Engineering
tags:
- LT
- JSP
- Servlet
---

この記事は CPS Lab Advent Calendar 2016 14日目の記事です．
http://www.adventar.org/calendars/1536

13日目は [@suconbu0909](https://twitter.com/sukonbu0909) の [初心者向けではないピンヘッダの使い方](http://sukonbu0909.hatenablog.com/entry/2016/12/13/140024) でした．

<!--more-->

先週は [ゼロから始めるプログラミング生活](http://harhogefoo.xyz/blog/2016/12/07/zero_kara_programming/) を書きました．

テレビ生活が充実している．逃げ恥10話を見た．
がっきーかわいい．
星野源うらやましい．
エンディングテーマの恋を作曲した星野源がかっこいいなぁと

某Slackでの叫び
[![https://gyazo.com/341e551f523738ea0f5334c037fc33cc](https://i.gyazo.com/341e551f523738ea0f5334c037fc33cc.png)](https://gyazo.com/341e551f523738ea0f5334c037fc33cc)

最近の趣向は，録りためた放送大学の番組を垂れ流しながら仕事すること
[データの分析と知識発見（'16）](http://www.ouj.ac.jp/hp/kamoku/H28/kyouyou/C/joho/1570188.html)

はい本題

背景
--

### macユーザが増えた
毎年I科恒例の演習，鯖プロではJSP/Servletを使ったWebアプリの企画，開発，発表が行われている．
講義はWindows & eclipseで解説がされるため，環境構築で躓くmacユーザはgoogle先生に問い合わせることでその課題を解決している...はず．
最近ConoHaを使ってデプロイする所まで講義で扱っているので実務に向けた演習でとっても良い．

今回はIntellJ IDEAでJSP/Servletの開発するための手順を書いていきます．
あと，warファイルのデプロイ方法まで．

### 実行環境

1.  mac OS Sierra 10.12.11
2.  Java 1.7.0_79
3.  IntelliJ IDEA 2016 1.4
4.  Tomcat 8.0.36

### eclipseじゃなくて，IntelliJ IDEAを使おうよ
Javaで開発するならIntellJがおすすめです．おすすめです．
学生アカウントを作成すれば1年間Pro版は無料．(2016/12/14 現在)
リンク: https://www.jetbrains.com/student/

JSP/ServletでHello, Worldを出力するまで
-------------------------------
下記を参考に．
http://librastudio.hatenablog.com/entry/2013/08/23/014706

もしTomcatをインストールしていない場合は，下記を参考に
http://www.task-notes.com/entry/20150720/1437361200

自分の環境でも試す．
Create Project
[![https://gyazo.com/17280dad7b39d4f8d42329e2a0f016df](https://i.gyazo.com/17280dad7b39d4f8d42329e2a0f016df.png)](https://gyazo.com/17280dad7b39d4f8d42329e2a0f016df)

Project名の決定
[![https://gyazo.com/f91d039902b65de91fdaa5d30545b32d](https://i.gyazo.com/f91d039902b65de91fdaa5d30545b32d.png)](https://gyazo.com/f91d039902b65de91fdaa5d30545b32d)

Tomcatでビルドをする設定をして...略 (上記のリンク参照）

Hello, Worldがブラウザ上に出力されればOK．

warファイルのデプロイ
------------
特に躓くところがここ
まず，IntelliJで開発したプロジェクトのwarファイルの場所を調べる．
上記の設定ができていれば，ファイル以下に生成されている．
```
/プロジェクトファイルが保存されいるファイルパス/out/artifacts/[プロジェクト名]_war_exploded
```
ターミナルで上記のディレクトリまで移動
```
$ cd /プロジェクトファイルが保存されているファイルパス/out/artifacts/
$ jar -cf [適当な名前].war .
```
これでwarファイルが生成される．

### warファイルを作成したらscpでサーバにデプロイ
以下は，さくらVPS, CentOSの場合（個人によって設定が違うので参考までに）
```
$ scp [適当な名前].war sakura:~/
```
tomcatのディレクトリに移動
```
$ mv ~/[適当な名前].war /usr/local/tomcat/webapps/
```
scpの先がtomcatのディレクトリでももちろんOK

※ Tomcatの仕様で，warファイルが更新された時点で自動で更新されます．
もし更新されていない場合は，暫く待ってあげるか tomcatを再起動するなどを試してみて下さい．

以上

8月に書こう書こうと思っていた記事が
Advent Calenderによって消化された瞬間であった．
