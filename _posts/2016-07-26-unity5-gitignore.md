---
title: Unity5 新規プロジェクトを作成した時に必ず行う設定と.gitignore
date: 2016-07-26 16:17:08
categories:
- Engineering
tags:
- Unity
- Git
---

# Unity Gitバージョン管理用設定

`Editor > ProjectSettings > Editor`
## Version Control
Mode を `Visible Meta Files`に変更

## Asset Serialization
Mode を `Force Text`に変更
競合が起きた時にマージ作業ができるようになる．

# .gitignore for Unity
いつも.gitignoreをggるのでメモ
{% gist c68f95b831c5132c65323f3aebabccb5 %}