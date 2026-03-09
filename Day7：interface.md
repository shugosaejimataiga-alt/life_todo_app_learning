

Day7：interface

interfaceとは

TypeScriptで
オブジェクトの「データの形」を定義する型。


interface User {
  name: string
  age: number
}


この場合

name → string
age → number

を持つオブジェクトだけが User型になる。




型チェック

const user: User = {
  name: "Taro",
  age: 20
}

→ 型が一致しているので OK



const user: User = {
  name: "Taro"
}

→ ageが無いのでエラー



const user: User = {
  name: "Taro",
  age: "20"
}

→ numberではなくstringなのでエラー



重要ポイント

interfaceは

「この形のオブジェクトであること」

を保証する。

つまり

プロパティが足りない → エラー
型が違う → エラー


PHPとの違い

TypeScript
interface = データ構造の型

PHP
interface = クラスが必ず実装するルール

同じ名前だが 役割は違う。