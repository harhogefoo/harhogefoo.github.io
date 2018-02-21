---
title: JavaScript 指定した範囲の連続した日付を出力する（+ プログラマ脳を鍛える会 vol.2βの解答)
date: 2016-08-06 02:18:08
categories:
- Engineering
tags:
- LT
---

### 動機

先日の勉強会でJavaScriptを使って連続した日付を出力する方法でハマっていたのでメモ．

#### 連続した日付を出力するコード例

開始日と終了日の差分を取って，その日数分(86400000ms = 1day)加算を繰り返すことで達成できる．

### 参考文献
[意外と知られていないJavaScriptのnew Date()の使用方法](http://iwb.jp/javascript-new-date-gettime/)
[【JavaScript】日付を自由にフォーマットする](http://www.ilovex.co.jp/blog/system/distributionsystem/javascript-5.html)
[2進数、10進数、16進数の相互変換](http://yas-hummingbird.blogspot.jp/2009/08/21016.html)
