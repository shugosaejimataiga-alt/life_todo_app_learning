

Day16：型設計練習（Condition）まとめ

1. Union型で「取りうる値」を制限できる

type RPE = 1 | 2 | 3 | 4 | 5
type ConditionStatus = "good" | "normal" | "bad"
type InjuryLevel = "none" | "light" | "serious"

→ 決まった値だけ許可する型を作れる。



2. 作った型を組み合わせてオブジェクト型を設計する

type Condition = {
  playerId: number
  date: string
  rpe: RPE
  condition: ConditionStatus
  injury: InjuryLevel
}

→ 小さな型を組み合わせてデータ構造を作る。



3. 型を指定してオブジェクトを作る

const conditionLog: Condition = {
  playerId: 1,
  date: "2026-03-11",
  rpe: 3,
  condition: "good",
  injury: "none"
}

→ 型に合わない値はエラーになる。



4. 型設計の基本

値の種類をUnion型で作る

それを組み合わせてオブジェクト型を作る

型を使ってデータを安全に管理する。


