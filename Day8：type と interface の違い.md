
Day8まとめ（type と interface）


TypeScriptで型を作る方法は2つ

type
interface

どちらも オブジェクトの型 を作れる。


type User = {
  name: string
  age: number
}


interface User {
  name: string
  age: number
}

違い

interface → オブジェクト専用
type → あらゆる型を作れる



typeで作れる型の例

Union型

type Status = "open" | "closed"

意味

Statusには
"open" または "closed"
しか入らない


重要ポイント

interface
→ オブジェクトだけ

type
→ オブジェクト + Union型 + 他の型



覚え方

interface = オブジェクト専用

type = なんでも型

Day8：type と interface の違いを学びました。