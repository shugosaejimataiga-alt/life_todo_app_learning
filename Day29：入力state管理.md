

Day29 入力state管理

Reactでは フォーム入力の値はstateで管理する。

まずstateを作る。
const [name, setName] = useState("")

これは

name → 現在の入力値
setName → 入力値を更新する関数

を意味する。



Reactフォームの基本構造

Reactのinputは次の形になる。

<input
  value={name}
  onChange={(e) => setName(e.target.value)}
/>

役割は次の通り。

value
inputに表示する文字を決める。

inputの表示 = name
つまり表示は stateによって決まる。

onChange
inputの値が変わったときに発生するイベント。

setName
stateを更新する関数。

setName(e.target.value)

これにより

入力された文字 → stateに保存
される。



入力の流れ

ユーザーが入力する。

三笘

すると

① onChange発生
setName("三笘")

② state更新
name = "三笘"

③ React再描画
value={name}

④ input表示更新
三笘


つまり

入力 → state更新 → React再描画 → 表示更新

という流れになる。



Reactフォームの重要な考え方

Reactでは

入力の本体 = state

である。

HTMLのinputが値を持つのではなく

React(state)が入力を管理する


valueを消した場合

もし

<input
  onChange={(e) => setName(e.target.value)}
/>

こうなると

input表示 → ブラウザ管理
state → React管理

になり、普通のHTML inputと同じ動きになる。



Reactフォームの基本パターン

Reactの入力フォームは必ず次の形になる。

value={state}
onChange={(e) => setState(e.target.value)}

意味

表示 = state
入力変更 → state更新



最重要まとめ

Reactではフォーム入力を stateで管理する。

value={state}
onChange={(e) => setState(e.target.value)}

によって

input表示 = state

となり、Reactが入力を制御する。

これを

Controlled Component
（制御コンポーネント）

という。