---
title: Unity5 ゲーム開発はじめの一歩 読了
date: 2016-07-26 16:51:08
categories:
- Engineering
tags:
- Unity
---

技術書を読んだのでレビュー．

# 対象読者
**プログラム入門的知識（if文，for文，関数の作り方など）を知っている**かつ
**Unity5をこれから始めようと思っている人**におすすめ．
2時間〜3時間程でサクッと作りながら読みきれる．

# 動機

今まで全てインターネット上でUnityを学習してきたので体系的に再学習をしたかった．

# 知見
```
コインプッシャーゲームというシンプルなゲームを開発．
★反復移動はMathf.Sin関数を使う
`Mathf.Sin(Time.time)`
反復運動が簡単に作れる

★物体の移動には**Rigidbody.MovePosition(Vector3)**を使うこと
今まで物体の移動をさせる際
以下のようにオブジェクトに直接Vector3を代入して移動させるような実装をしていた．
`gameObject.transform.position += Vector3のhogehoge`
```
[Unityリファレンス - Rigidbody.MovePosition](http://docs.unity3d.com/jp/current/ScriptReference/Rigidbody.MovePosition.html)
リファレンスによると，移動をすることで物体に接触判定がある場合は`Rigidbody.MovePosition`を使ったほうがいいことがわかる．

## CoinPusherプロジェクトhttps://github.com/harhogefoo/CoinPusher
