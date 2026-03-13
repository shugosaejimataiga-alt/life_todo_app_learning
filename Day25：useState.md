

Day25：useState（Reactの状態管理）

1. stateとは
Reactで画面に表示されるデータを管理する仕組み。
stateが変わると Reactは画面を再描画する。



2. useStateの書き方

const [state, setState] = useState(初期値);

意味
state → 現在の値
setState → 値を変更する関数

初期値 → 最初の値


例

const [count, setCount] = useState(0);

count → 現在の値
setCount → 値を変更する関数
0 → 初期値



3. stateの表示

<h1>{count}</h1>

JSXでは {}の中にstateを書くと表示できる。



4. stateの変更方法

stateは 直接変更できない。

❌ 間違い
count = 1

⭕ 正しい
setCount(1)

理由
Reactは setStateが呼ばれた時に画面更新を行うため。



5. useStateの基本構造

state = 現在の値
setState = 値を更新する関数
useState() = stateを作るReactの関数



6. 例（名前のstate）

const [name, setName] = useState("三笘");

name → 現在の値
setName → 値変更
"三笘" → 初期値

変更

setName("久保")



今日の最重要ポイント

Reactでは 画面データはstateで管理し、値はsetStateで変更する。
