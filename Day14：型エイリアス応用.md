

Day14 型エイリアス応用


① 型エイリアスとは

type を使うと 型に名前を付けて再利用できる

type Position = "GK" | "DF" | "MF" | "FW"

Position型には
GK / DF / MF / FW しか入らない



② 他の型で使える

type Player = {
  name: string
  position: Position
}

ここで

position: Position

とすると

positionには

"GK"
"DF"
"MF"
"FW"

しか入れられない。



③ 型にない値はエラー

const player: Player = {
  name: "Taro",
  position: "CB"
}

CBはPosition型に存在しないため
TypeScriptエラーになる



④ 数字でも同じ

type RPE = 1 | 2 | 3 | 4 | 5
let rpe: RPE = 3

OK

let rpe: RPE = 6

❌ エラー



今日の本質

typeで型を作り、その型を他の型で使って、許可する値を制限する。


