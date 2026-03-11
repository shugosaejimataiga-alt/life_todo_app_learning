

Day20
TypeScriptまとめ（Day1〜Day19総復習）



① TypeScriptの目的

TypeScriptは

データの形（型）を決めて
エラーを防ぐ言語

JavaScriptは自由に値を入れられるため、
意図しない型のデータが入ってバグが起こる。

TypeScriptでは

データの型を先に決める

ことで安全にコードを書く。




② 基本型

データの基本的な種類。

number
string
boolean

例

let age: number = 28
let name: string = "三笘薫"
let injured: boolean = false



③ 配列型

同じ型のデータが複数入る。

書き方
型[]

例
let scores: number[] = [1,2,3]
let names: string[] = ["三笘","久保"]



④ オブジェクト型

複数の種類のデータをまとめる。

例

let player = {
 name: "三笘",
 age: 28
}

TypeScriptでは型を書く。

{
 name: string
 age: number
}



⑤ 型付きオブジェクト

オブジェクトの型を指定する。

const player: {
 name: string
 age: number
} = {
 name: "三笘",
 age: 28
}

型が違うとエラーになる。




⑥ type

オブジェクト型を再利用できる。

type Player = {
 name: string
 age: number
}

使用

const player: Player = {
 name: "三笘",
 age: 28
}



⑦ interface

typeと同じく
オブジェクトの型を定義できる。

interface Player {
 name: string
 age: number
}



⑧ type と interface の違い

基本的には どちらも型定義。

type
interface

Reactでは両方使われる。




⑨ 関数の型

関数の引数と戻り値の型を決める。

function add(a: number, b: number): number {
 return a + b
}



⑩ 戻り値の型

関数が返すデータの型。

function getName(): string {
 return "三笘"
}



⑪ Union型

複数の値のどれかを許可。

type Position = "GK" | "DF" | "MF" | "FW"



⑫ Optionalプロパティ

必須ではないデータ。

age?: number

書かなくてもよい。




⑬ readonly

変更できない値。

readonly id: number



⑭ 型エイリアス応用

Unionなどを組み合わせて型を作る。

例

type RPE = 1 | 2 | 3 | 4 | 5



⑮〜⑱ 型設計練習

実際のアプリのデータを設計した。

Player
type Player = {
 id: number
 name: string
 position: "GK" | "DF" | "MF" | "FW"
 dominantFoot: "右足" | "左足" | "両足"
}

Condition
type Condition = {
 playerId: number
 date: string
 rpe: 1 | 2 | 3 | 4 | 5
 condition: string
}

Physical
type Physical = {
 playerId: number
 weight: number
 bodyFat: number
 sprint50m: number
 jump: number
}

Tactic

戦術ボード用のデータ。

選手位置
ボール
ライン
矢印

などをデータとして管理する。




⑲ JSON型設計

LaravelからReactに送られるデータは
JSON形式。

単体
{}

配列
[]

例

{
 id:1,
 name:"三笘"
}

これは
Player


配列
[
 {id:1,name:"三笘"},
 {id:2,name:"久保"}
]

これは
Player[]



⑳ Phase1の本質

TypeScriptは

アプリのデータ設計

である。

アプリはすべてデータで動く。

選手
体調
フィジカル
戦術

そのデータの形を

TypeScriptで定義する
Phase1で身についたこと

あなたは

Player
Condition
Physical
Tactic

などの

アプリのデータ構造

をTypeScriptで設計できるようになった。




最重要理解
TypeScript = データの設計図

これが
Day1〜Day20の核心です。


