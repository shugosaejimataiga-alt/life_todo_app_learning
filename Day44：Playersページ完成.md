

Day44 完全まとめ


■ 今日やったこと（本質）

👉 1つの画面を役割ごとに分割した



■ 分割前（元の状態）

全部1ファイル（Players.tsx）

・入力フォーム
・一覧表示
・状態管理
・処理


■ 分割後（現在）

Players（親）
 ├ PlayerForm（入力）
 └ PlayerList（一覧）


■ 役割の違い

● Players（親）
👉 すべて管理

state
players（データ）
form（入力）
editingPlayer（編集）

処理
add / delete / update / validate


● PlayerForm（子）
👉 入力だけ

名前入力
ポジション選択
追加 / 更新ボタン


● PlayerList（子）
👉 一覧だけ

選手表示
削除ボタン
編集ボタン



■ データの流れ（超重要）

Players（state持つ）
  ↓ propsで渡す
PlayerForm / PlayerList
  ↓ 操作（クリック・入力）
Playersの関数が動く


■ Propsの本質
👉 子が使うものだけ渡す

PlayerFormに渡すもの

form
setForm
editingPlayer
addPlayer
updatePlayer

👉 理由：フォーム内で使っているから


PlayerListに渡すもの

players
deletePlayer
setEditingPlayer

👉 理由：一覧で使っているから



■ 分け方のルール（超重要）

👉 子コンポーネントの中を見る
👉 出てくる変数を全部渡す


■ 絶対ルール

👉 stateは親に置く
👉 UIは子に分ける


■ 何をしたのか（シンプルに）
👉 コードを分けただけ（ロジックは変えていない）


■ 完成している機能

追加
削除
編集
バリデーション
編集時フォーム反映

👉 CRUD完成


■ 核心（これだけ覚えればOK）

👉 親＝管理、子＝表示
👉 Props＝子が使うものだけ渡す