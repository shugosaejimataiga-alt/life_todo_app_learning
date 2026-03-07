
Day2まとめ（完全復習）


① 型とは何か（前提）

TypeScriptは

「変数に入るデータの種類を先に決める言語」

でした。

例

let age: number = 20;


意味

age という変数を作る
number型（数字）しか入らない



② 基本型① number

数字を扱う型

let age: number = 20;
let price: number = 1000;


入れられるもの

1
20
3.14
-5


入れられないもの

"hello"
true

理由
数字ではないから



③ 基本型② string

文字を扱う型

let name: string = "Shu";
let title: string = "My Dream";


入れられるもの

"hello"
"Dream"
"123"

※ " " がつくと文字になる


入れられないもの

20
true


④ 基本型③ boolean

真偽を扱う型

let isOpen: boolean = true;
let isLogin: boolean = false;


入るもの

true
false


入らないもの

1
"true"


⑤ TypeScriptのチェック

TypeScriptは

変数の型
=
入れる値の型

が 一致しているかをチェックする



例

OK

let title: string = "Dream";
title = "New Dream";

理由
string ← string



エラー

let age: number = 20;
age = true;

理由
number ← boolean
型が違う



⑥ 今日の核心

TypeScriptは

number   → 数字
string   → 文字
boolean  → 真偽

この 3つの基本型を守ることでバグを防ぐ言語。



⑦ 超重要理解（今後の土台）

今後学ぶもの

配列

オブジェクト

React

API

データ設計

すべて

number
string
boolean

この組み合わせで作られる。



最終一行まとめ

TypeScriptは 変数に入るデータの種類（型）を決め、number / string / boolean の基本型でデータの安全性を守る言語。