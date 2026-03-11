

Day15 型設計練習（Player）


1 型設計とは

アプリで扱うデータの形（構造）を先に決めること。
これにより、データのミスをTypeScriptが自動で検出できる。

例：サッカー選手なら

name
age
position
dominantFoot

のような情報を持つ。




2 TypeScriptで型を作る（type）

type Player = {
  name: string
  age: number
  position: "GK" | "DF" | "MF" | "FW"
  dominantFoot: "右足" | "左足" | "両足"
}

意味

name → 文字
age → 数字
position → GK / DF / MF / FW のどれか
dominantFoot → 右足 / 左足 / 両足 のどれか

Union型で選択肢を限定できる。




3 型を使ってオブジェクトを作る

const player: Player = {
  name: "三笘薫",
  age: 28,
  position: "MF",
  dominantFoot: "右足"
}

ポイント

プロパティ: 値

オブジェクトでは
= ではなく : を使う




4 TypeScriptが守ってくれること

例えば

const player: Player = {
  name: "久保建英",
  age: "22",
  position: "MF",
  dominantFoot: "左足"
}

これはエラーになる。

理由

age: "22"
は string

しかし型は

age: number
なので型違いエラーになる。




5 今日の本質（最重要）

TypeScriptでは

① データの型を設計する
② その型を使ってデータを作る

この流れでアプリを作る。

つまり

型設計 → データ作成 → アプリ開発




6 今日のゴール

Day15では

サッカー選手データの型を設計できるようになった

Player型

を作り

name
age
position
dominantFoot

を安全に管理できるようになった。




7 将来のアプリとの関係

このPlayer型は

選手管理
コンディション管理
フィジカルログ
戦術ボード

などすべての機能の土台になるデータ構造。


