---
title: Unity5/C# 固有IDを生成する
date: 2016-08-16 02:05:08
categories:
- Engineering
tags:
- Unity
- C#
---

Unityで端末の固有IDを取得しようとした
----------------------

### 動機

Unityで開発したアプリのユーザのバックアップ，リストア機能を実装する上で
複数端末からのログインを防ぐため．

以下のコードでtokenが取得できるらしいが
{% highlight csharp %}
// Unity5.4.0f3では，以下のtokenはnullで返ってきた.
byte[] token = UnityEngine.iOS.NotificationServices.deviceToken;
{% endhighlight %}

参考: [UnityからiOS・Androidの機器情報を取得　メモ](http://qiita.com/satotin/items/10bad380abfb6b875bb1)

以下のリンクから，機器情報を取得することに対して制約があることがわかった．
[Unity任せの機種固有ID取得は危険！-Unityアプリで効果計測を行う際の注意点-](http://blog.admage.jp/?p=894)

### 解決策

端末を固有に認識するなら，端末に固有のIDを割り振ればいいので以下のスクリプトで解決できる

後はこのUUIDをユーザと紐つけてサーバに保存して運用をする．
