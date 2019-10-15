# smartround-tech-presentation
外部の人向けにsmartroundを支える技術の紹介

## Overview

### Useage
「外部の人向けにsmartroundを支える技術の紹介」のスライドをGitPitchで作成するためのレポジトリです。

### Requirement
 * Github account

### Directory Structure
```
Repository
 ├ README.md
 ├ PITCHME.md     #スライド本体
 ├ PITCHME.yaml   #スライド設定ファイル
 └ assets
       ├ img      #挿入用イメージフォルダ
       └ css      #設定用cssフォルダ
 ```
 
### Reference
<a href="https://gitpitch.com/docs/getting-started/">GitPitch</a>

## How to create a slide
 * スライドのコンテンツについて
 スライド内の中身を変更したい場合は「PITCHME.md」を変更します。なお、Markdown記法で書きます。
 
 * ページの区切り
 スライドのページを区切るためには「---」をページ下部に挿入します。
 ```
 # Page1
 Page1 content
 
 ---
 
 # Page2
 Page2 content
 ```
 
 ## How to develope in local enviroment
  * ローカルでの開発を行う場合はあらかじめgit cloneしたファイルを編集して、git pushしてください。
  * ローカルでのプレビューはpro版のみの対応になっています。ただ、freeでもローカルでプレビューをできるDocker imageを作っている人がいたので載せます。
  ### How to preview with free acount in local enviroment
  Reference: https://qiita.com/uzimaru0000/items/a7082b9acc73d16c3df5
  ※公式の方法ではないので、バグが出る場合があります。
  
