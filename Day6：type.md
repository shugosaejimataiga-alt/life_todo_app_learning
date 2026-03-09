

Day6：type


1. typeとは

型に名前をつける機能

type User = {
  name: string
  age: number
}

意味

User = name と age を持つ型の設計図



2. 型を使う

const user: User = {
  name: "Taro",
  age: 20
}


構造

User → 型（設計図）
user → 実際のデータ



3. 再利用できる

const a: User = {
  name: "Ken",
  age: 30
}

const b: User = {
  name: "Mika",
  age: 25
}

同じ型を何度でも使える。




4. 型エラーの例

① 型違い

age: "20"
number 必須  
string を渡した  
→ エラー


② 型違い

name: 100
string 必須  
number を渡した  
→ エラー



③ プロパティ不足

const user: User = {
  name: "Taro"
}
age がない  
→ エラー



5. 今日の核心

type = 型に名前を付ける

type User = { ... }

これにより

型を再利用できる
コードが整理される



1行で覚える

type = オブジェクトの型に名前を付ける仕組み