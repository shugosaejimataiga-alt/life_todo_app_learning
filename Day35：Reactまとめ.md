

Day35 React基礎まとめ

Reactでは UIをコンポーネント（関数）という部品の組み合わせで作る。
コンポーネントは JSXを返す関数であり、JSXはHTMLのようにUIを書く構文だが、{} を使うことでJavaScriptの値や式を表示できる。

画面のデータは state（useState） で管理される。
useState は 現在のデータ(state)と更新関数(setState) を持ち、更新関数が実行されると Reactが再描画してUIが自動更新される。

配列データを画面に表示する場合は map() を使い、配列の要素を1つずつ取り出して JSXを生成することでリスト表示を実現する。

ユーザー操作は イベント処理（onClick / onChangeなど） で受け取り、フォーム入力では

onChange={(e) => setName(e.target.value)}

のように 入力値をstateに保存して画面データを管理する。

Reactアプリではこれらを組み合わせて CRUD（Create / Read / Update / Delete） を実装する。

追加（Create）

表示（Read）

編集（Update）

削除（Delete）

また、コードが大きくなった場合は コンポーネント分割を行い、

components/
  PlayerForm.tsx
  PlayerList.tsx

のように 役割ごとにファイルを分けて管理する。

最終的にReactは

state（データ）
 ↓
JSX（UI生成）
 ↓
画面表示
 ↓
ユーザー操作
 ↓
state更新
 ↓
React再描画

という **「stateを中心にUIが自動更新される仕組み」**で動く。