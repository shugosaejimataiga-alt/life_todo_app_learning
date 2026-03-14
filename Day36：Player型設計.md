

Day36：Player型設計

このフェーズでは、サッカーチーム管理アプリで扱う**選手データの構造（型）**をTypeScriptで設計する。

アプリでは選手の情報を1つのオブジェクトとして管理するため、まず Player型 を定義する。

type Player = {
  name: string
  position: "GK" | "DF" | "MF" | "FW"
  number: number
  age?: number
}


各プロパティの意味

name
選手名（文字列）

position
ポジション（GK / DF / MF / FW の4種類のみ）

number
背番号（数値）

age
年齢（数値）
? を付けることで Optional（任意）プロパティ になり、書かなくてもよい。


TypeScriptでは、型と違うデータを入れるとエラーになる。

例
age: "28"

これは文字列なので number型と一致せずエラーになる。
また、必須プロパティが不足している場合もエラーになる。


次に、アプリでは選手を1人ではなく複数管理するため、型は配列になる。

const players: Player[] = [
  { name: "三笘薫", position: "MF", number: 7, age: 28 },
  { name: "久保建英", position: "FW", number: 10, age: 23 }
]

ここで重要な理解

Player
→ 選手1人

Player[]
→ 選手のリスト（複数）

Reactアプリでは、この Player[] をstateで管理し、map()で画面表示する ことで選手一覧を作る。