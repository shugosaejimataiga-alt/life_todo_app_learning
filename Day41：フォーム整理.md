

Day41 フォーム整理（完全まとめ）


■ 目的

入力フォームの状態（name / position）をバラバラに管理するのをやめて、1つのオブジェクト（form）としてまとめて管理する。



■ Before（問題点）

const [name, setName] = useState("")
const [position, setPosition] = useState("GK")

stateが分散している

項目が増えると管理が複雑になる

追加・編集でロジックがバラバラになる



■ After（今回の変更）

const [form, setForm] = useState({
  name: "",
  position: "GK"
})

👉 入力データを「1つのまとまり」として扱う



■ 各修正ポイント

① useEffect（編集時の値セット）
setForm({
  name: editingPlayer.name,
  position: editingPlayer.position
})

👉 個別代入 → 一括代入へ変更


② input
value={form.name}
onChange={(e)=>setForm({
  ...form,
  name: e.target.value
})}

👉 form全体をコピーして、一部だけ更新


③ select
value={form.position}
onChange={(e)=>setForm({
  ...form,
  position: e.target.value
})}

👉 inputと同じ構造


④ addPlayer
name: form.name,
position: form.position

👉 formからデータ取得


⑤ updatePlayer
name: form.name,
position: form.position

👉 編集もformで統一


⑥ 不要state削除
name, position は削除

👉 formに統一されたため不要



■ 超重要概念（今回の核）

● setStateは「上書き」

setForm({
  name: "三笘"
})

👉 positionが消える


● だからコピーが必要
setForm({
  ...form,
  name: "三笘"
})

👉 一部だけ変更できる



■ 今のstate構造
players         // データ本体
form            // 入力中のデータ
editingPlayer   // 編集対象

👉 役割が完全に分離



■ 何が成長したか

① データの扱い方が変わった
バラ管理 → オブジェクト管理

② 処理が統一された
追加と編集が同じデータ構造

③ 拡張性が上がった
form.age
form.height
form.weight

👉 stateを増やさずに対応できる



■ 見た目が変わらない理由

👉 今回はUIではなく「設計の改善」

動き → 同じ

中身 → 大きく進化



■ 現在の状態（到達点）

CRUD完成

formで入力一元管理

編集との連携も完了

👉 実務レベルの基本構造に到達



■ 一言まとめ

👉 入力データをバラバラに扱うのをやめて、
👉 「formという1つのオブジェクトで管理する構造」に進化した