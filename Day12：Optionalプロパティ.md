

Day12 Optionalプロパティ（完全復習）

Optionalプロパティとは

TypeScriptでは
プロパティの後ろに ? を付けると「そのプロパティは無くてもよい」
という意味になる。



基本構文

type Player = {
  name: string
  age: number
  injury?: string
}

意味

name → 必須
age → 必須
injury → 任意（Optional）



許されるデータ

injuryが無い場合

const p1: Player = {
  name: "Taro",
  age: 20
}


injuryがある場合

const p2: Player = {
  name: "Taro",
  age: 20,
  injury: "ankle"
}

どちらも OK


必須プロパティが欠けるとエラー

const p3: Player = {
  name: "Taro"
}

これは エラー

理由
age が必須だから



Optionalにすると省略できる

type Player = {
  name: string
  age?: number
}
const p: Player = {
  name: "Taro"
}

これは OK

理由
age は Optional（?）だから



今日の重要ポイント

1️⃣ ? を付けると Optionalプロパティになる

2️⃣ Optionalプロパティは
書いてもいい / 書かなくてもいい

3️⃣ ? が付いていないプロパティは
必須（必ず書く）


一瞬で思い出すキーワード
? = Optional = あってもなくてもOK