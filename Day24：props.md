

Day24：props


1. コンポーネント

Reactでは UIの部品をコンポーネントとして作る。

function Player() {
  return <h2>Player</h2>
}


2. 親コンポーネントと子コンポーネント

コンポーネントの中で別のコンポーネントを使うと親子関係になる。

function Player(){
  return <p>Player</p>
}

function App(){
  return <Player />
}

この場合

App → 親コンポーネント
Player → 子コンポーネント

理由
Appの中でPlayerを使っているから。

App（親）
 └ Player（子）



3. propsとは

親コンポーネントから子コンポーネントへデータを渡す仕組み。



4. propsの書き方

親コンポーネント（データを渡す）
<Player name="三笘" />

ここで

name="三笘"

が props。



子コンポーネント（データを受け取る）

function Player(props:{name:string}) {
  return <h2>{props.name}</h2>
}
props.name

で 渡されたデータを使える。




5. データ・コンポーネント・propsの違い

例

<Player name="三笘" />

整理

Player → コンポーネント
三笘 → データ
name="三笘" → props



6. propsは複数渡せる

<Player name="三笘" position="MF" />

子コンポーネント

function Player(props:{name:string, position:string}) {
  return <p>{props.name} - {props.position}</p>
}

表示

三笘 - MF




今日の核心

props = 親コンポーネントから子コンポーネントへデータを渡す仕組み

流れ

親コンポーネント
   ↓ props
子コンポーネント


