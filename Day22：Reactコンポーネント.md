

Day22 Reactコンポーネント

Reactでは 画面を「コンポーネント」という部品に分けて作る。



① コンポーネントとは

UI（画面）を返す関数

例

function Header() {
  return <h1>Team Manager</h1>
}

意味

function Header()
→ Headerというコンポーネントを作る

return
→ 画面に表示するUIを書く




② コンポーネントの使用

コンポーネントは HTMLタグのように使う

<Header />

すると

<h1>Team Manager</h1>

が表示される。




③ コンポーネントは組み合わせる

Reactでは

UI = コンポーネントの組み合わせ

例

function Header() {
  return <h1>Team Manager</h1>
}

function App() {
  return (
    <div>
      <Header />
      <p>Welcome</p>
    </div>
  )
}

表示

Team Manager
Welcome



④ 同じコンポーネントは何度でも使える

function Player() {
  return <p>三笘薫</p>
}

function App() {
  return (
    <div>
      <Player />
      <Player />
      <Player />
    </div>
  )
}

表示

三笘薫
三笘薫
三笘薫

理由
同じコンポーネントを 再利用できるため。




⑤ Reactの基本思想

Reactでは

画面 = コンポーネントの集合

例（サッカー管理アプリ）

App
 ├ Header
 ├ PlayerList
 │   ├ PlayerCard
 │   ├ PlayerCard
 │   └ PlayerCard
 └ Footer

小さな部品を作り、それを組み合わせてUIを作る。




Day22 最重要ポイント

コンポーネント = UIを返す関数

return に HTMLを書く

使うときは <Component />

コンポーネントは何度でも再利用できる

Reactでは UI = コンポーネントの組み合わせで作る。


