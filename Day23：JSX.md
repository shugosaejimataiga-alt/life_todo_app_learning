

Day23 JSX（React）

JSXとは
JavaScriptの中でHTMLのようにUIを書く React専用の構文。

基本構造

function App() {
  return (
    <h1>Hello</h1>
  )
}

Reactコンポーネントは JSXをreturnして画面を作る。

JSXの重要ルール



① returnは1つの親要素

❌ エラー

return (
  <h1>Player</h1>
  <p>Welcome</p>
)


⭕ 正しい

return (
  <div>
    <h1>Player</h1>
    <p>Welcome</p>
  </div>
)

Reactでは 必ず1つの要素として返す必要がある。



② { }の中ではJavaScriptが書ける

const player = "三笘薫"

<h1>{player}</h1>

表示

三笘薫




③ 変数・計算・式が使える

{player}
{5 + 3}
{player + "選手"}

例

const goals = 2
const assists = 1

<h1>{goals + assists}</h1>


表示

3




JSXの構造（重要）

JSX（HTMLの形）
     ↓
{ } の中はJavaScript
     ↓
値・計算結果が表示される



最重要まとめ（1文）

JSXはReactでUIを書く構文で、{}を使うとJavaScriptの値や計算結果を画面に表示できる。


