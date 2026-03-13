

Day27 Reactイベント処理（完全整理）


1. Reactのイベントとは

ユーザーの操作（クリック・入力など）が起きたときに 関数を実行する仕組み。

例：ボタンがクリックされたとき

function addPlayer() {
  console.log("player added")
}

<button onClick={addPlayer}>
  Add Player
</button>

クリックすると
addPlayer()
が実行される。



2. Reactのイベントの書き方

Reactでは

onClick={関数}

という形で書く。


ポイント

onClick の Cは大文字
{} の中は JavaScript
関数そのものを渡す



3. HTMLとの違い

HTML

<button onclick="addPlayer()">

React

<button onClick={addPlayer}>


違い

HTML → 文字列
React → JavaScriptの関数



4. {} の意味

JSXでは

HTMLを書く部分

<h1>Team Manager</h1>

JavaScriptを書くとき

{JavaScript}

イベントもJavaScriptなので

onClick={addPlayer}

となる。



5. () を付けてはいけない理由

正しい

<button onClick={addPlayer}>

意味
「クリックされたときに addPlayer() を実行」



間違い

<button onClick={addPlayer()}>

これは

画面表示時
addPlayer() が すぐ実行される

つまり

クリックとは関係なく実行されてしまう



6. Reactイベントの基本ルール

必ず覚える

onClick={関数}


ポイント

Reactは onClick

{} は JavaScriptを書く場所

関数を渡す

() は付けない



7. Day27で理解すべき本質

Reactでは

UI（JSX）と処理（JavaScript関数）を結びつける

つまり

ボタン → onClick → 関数実行

構造

UI
↓
イベント
↓
関数
↓
処理



8. 今後のReactでの使い道

イベント処理は次で使う

選手追加
選手削除
編集
フォーム送信

つまり

Reactアプリの操作は全部イベントから始まる




最短記憶（1行）

Reactのイベントは onClick={関数} で書き、クリック時に関数を実行する。() を付けると即実行されるため付けない。