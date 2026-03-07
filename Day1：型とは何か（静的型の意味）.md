

📘 Day1 完全まとめ（TypeScript基礎）


🎯 今日のゴール

型とは何かを理解

tscの意味を理解

モジュールの概念を理解




Day1：型とは何か（TypeScript）


① 型とは

変数に入れてよいデータの種類を決めるルール

例

let age: number

意味

ageには数字しか入らない



② JavaScriptの問題

JavaScriptは型がないので

let age = 20
age = "twenty"

のようなことができてしまう。

その結果

"twenty" + 10 = "twenty10"

のような バグが起きる。



③ TypeScriptの役割

TypeScriptは

let age: number = 20
age = "twenty"

と書くと

型エラー

を出して バグになる前に止めてくれる。



④ 基本の型

number  → 数字
string  → 文字
boolean → true / false

例

let age: number = 20
let name: string = "Taro"
let isOpen: boolean = true
今日の核心

TypeScriptは

「変数に入るデータの種類を先に決めて、バグを防ぐ言語」





🟦 フォルダ作成と環境準備

Cドライブへ移動
cd \

フォルダ作成
mkdir life_todo_app_learning

フォルダに入る
cd life_todo_app_learning



🟦 Node / npm 確認

node -v
npm -v

Nodeとnpmが入っていることを確認。



🟦 TypeScript インストール

グローバルインストール
npm install -g typescript

確認
tsc -v

ここでバージョンが出ればOK。







🟦 tscとは何か

tsc index.ts

これは実行ではない。

tscの役割

.ts → .js に変換（コンパイル）する。



流れ

index.tsを書く

tscで変換

index.jsが生成される

nodeがjsを実行する

TypeScriptは直接動かない。



🟦 なぜ .ts はエラーで .js はエラーにならない？

TypeScript → 型をチェックする
JavaScript → 型をチェックしない

TypeScriptのエラーは

「実行不能エラー」ではなく
「型ルール違反エラー」



🟦 勝手に.jsができた理由

tscを実行すると

index.ts
↓
index.js が新しく生成される

tsは消えない。
jsは変換後の成果物。



🟦 赤線エラーの正体

原因：

他のファイルと変数が衝突（グローバル扱い）

解決：

export {}

これでファイルを「モジュール」にする。



🟦 モジュールとは

モジュール＝

他ファイルと分離された独立空間。

モジュールにすると：

変数が混ざらない

import/exportでやり取りする

Reactでは全てモジュール前提。



🎯 Day1で理解した核心

TypeScriptは直接動かない

tscは変換コマンド

nodeが実行する

モジュールはファイルを独立させる
















② Git初期化（最初に必ずやる）
git init

③ .gitignore作成（VSCodeで作る）
.gitignore の中身：

node_modules
*.js


④ 現在の状態確認
git status

⑤ 追加
git add .

⑥ 初コミット
git commit -m "Day1 TypeScript setup"

⑦ GitHubリポジトリ接続
git remote add origin https://github.com/shugosaejimataiga-alt/life_todo_app_learning.git
git branch -M main

⑧ 初回push
git push -u origin main


🎯 覚えるべき流れ
git init
↓
git add .
↓
git commit
↓
git push

これが基本形です。

これでDay1完全終了です。





Day1：型とは何か（静的型の意味）