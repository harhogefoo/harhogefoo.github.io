---
title: Unity5 特定の方向に向かって回転するスクリプト
date: 2016-07-25 14:41:08
categories:
- Engineering
tags:
- Unity
---

# Quaternion.LookRotation
[Quaternion.LookRotation](http://docs.unity3d.com/jp/current/ScriptReference/Quaternion.LookRotation.html)
この関数を利用すれば簡単に作れる

# 原点の方向に向かって回転する
今回は原点に向かってカメラを回転させたかったので，
原点オブジェクト（Origin)を `new GameObject`で生成．

# 参考文献
徐々に回転させながら回転するスクリプトは以下のリンクを参考にするといいと思う．
[Unity tips 2 カメラスクリプトの書き方](http://numalog.relva.org/?p=186)
