

Day33 コンポーネント分割（完全まとめ）


1. Reactコンポーネントとは

Reactでは コンポーネント = 関数 です。

function PlayerForm() {
  return <input />
}

この関数は JSXを返す関数です。



2. <Component /> の正体

Reactで

<PlayerForm />

と書くと内部では

PlayerForm()

という 関数実行 が行われます。

流れ

<PlayerForm />
↓
PlayerForm() が実行
↓
return <input />
↓
<input> が画面に表示

つまり

コンポーネントは JSX を返す関数であり、
その return がそのまま画面に表示される。



3. {} の役割

{} は JSXの中でJavaScriptを書くための記法です。

例

const name = "三笘"

return <h1>{name}</h1>

表示

三笘

つまり

JSXの中で変数や式を使うとき → {}



4. コンポーネント分割の理由

最初のReactアプリはこうなりがちです。

App
 ├ 入力フォーム
 ├ 追加ボタン
 └ Player一覧

すべてを App.tsx に書くと

コードが巨大になる
読めなくなる
管理できなくなる



5. 解決方法

Reactでは 機能ごとにコンポーネントを分割する

例

App
 ├ PlayerForm
 └ PlayerList

役割

App
アプリ全体を管理

PlayerForm
選手追加フォーム

PlayerList
選手一覧表示



6. 分割したコード例

App

import PlayerForm from "./PlayerForm"
import PlayerList from "./PlayerList"

function App() {
  return (
    <div>
      <h1>Team Manager</h1>

      <PlayerForm />
      <PlayerList />

    </div>
  )
}

export default App

PlayerForm

function PlayerForm() {
  return <input />
}

export default PlayerForm



7. React設計の基本思想

Reactでは

UI = コンポーネントの集合

つまりアプリは

App
 ├ Header
 ├ PlayerForm
 ├ PlayerList
 └ Footer

のように

小さな部品を組み合わせて作る。



今日の核心

Reactでは

コンポーネント = JSXを返す関数

そして

<Component />
↓
関数実行
↓
returnされたJSXが画面表示

アプリが大きくなったら
機能ごとにコンポーネントを分割する
これが Reactの基本設計 です。