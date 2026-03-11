

Day19：JSON型設計


① JSONとは

Laravel → React にデータを送る形式

例

{
  id: 1,
  name: "三笘薫",
  position: "MF"
}



② JSONの基本構造

JSONには 2種類の形がある。

オブジェクト {}

例

{
 id: 1,
 name: "三笘薫"
}


配列 []

例

[
 { id: 1, name: "三笘薫" },
 { id: 2, name: "久保建英" }
]



③ TypeScriptの型との関係

JSONの形によって TypeScriptの型が決まる。

オブジェクト {}

↓

Player
ConditionLog
PhysicalLog


配列 []

↓

Player[]
ConditionLog[]
PhysicalLog[]



④ 例（Player）

Laravelが返すJSON
{
 id: 1,
 name: "三笘薫",
 position: "MF"
}

React
↓
Player



Laravelが返すJSON
[
 { id: 1, name: "三笘薫", position: "MF" },
 { id: 2, name: "久保建英", position: "FW" }
]

React
↓
Player[]



⑤ 実際のReactコード

例
const players: Player[] = data

意味

playersには
Player型の配列が入る



⑥ 今日の学習の目的

Reactでは APIから来るJSONをTypeScriptの型で受け取る。

そのため

JSONの形を見る
↓
TypeScriptの型を書く

という作業が必要になる。




⑦ 今日覚える最重要ルール

{}  → 型
[]  → 型[]

例

{} → Player
[] → Player[]

{} → PhysicalLog
[] → PhysicalLog[]



⑧ 一言まとめ

JSONの形を見てTypeScriptの型を決める。

