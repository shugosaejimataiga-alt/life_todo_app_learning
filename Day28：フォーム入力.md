

Day28 フォーム入力（React）

Reactでは 入力フォームの値を state で管理する。
ユーザーが入力 → onChange 発火 → e.target.value で入力値取得 → setState で state 更新 → Reactが再描画、という流れでUIが更新される。


基本コード

import { useState } from "react"

function App() {

  const [name, setName] = useState("")

  return (
    <div>

      <input
        type="text"
        value={name}
        onChange={(e) => setName(e.target.value)}
      />

      <p>{name}</p>

    </div>
  )
}

export default App
各部分の役割



① state作成

const [name, setName] = useState("")

name → 現在の入力値
setName → state更新関数
"" → 初期値



② inputとstateを同期

value={name}

意味
inputの表示値 = state

つまり

stateが変わると
inputの表示も変わる



③ 入力イベント

onChange={(e) => setName(e.target.value)}


意味

onChange → 入力が変わると発火

e → イベント情報

e.target → input要素

e.target.value → 入力された文字




④ state更新

setName(e.target.value)

入力された文字を
nameのstateに保存


処理の流れ（最重要）

ユーザー入力

例

三笘

↓

onChange発火

↓

e.target.value = "三笘"

↓

setName("三笘")

↓

name = "三笘"

↓

React再描画

↓

UI更新



Reactフォームの基本構造

const [state, setState] = useState("")

<input
  value={state}
  onChange={(e) => setState(e.target.value)}
/>

覚えるべき構造

value = state
onChange → setState



重要キーワード
| 要素             | 意味    |
| -------------- | ------- |
| useState       | 状態管理  |
| value          | inputの値 |
| onChange       | 入力イベント  |
| e.target       | input要素 |
| e.target.value | 入力された文字 |
| setState       | state更新 |
| 再描画            | UI更新  |



今日の核心（超重要）

Reactでは

入力値はDOMではなく state で管理する

つまり

input = stateの表示
入力 = state更新
