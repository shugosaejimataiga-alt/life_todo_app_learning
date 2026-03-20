

Day53 完全まとめ（選手別表示）


■ 今日やったこと

Condition履歴を
👉 選手ごとに絞って表示する機能を実装



■ 実装内容

① 選択状態の追加
const [selectedPlayerId, setSelectedPlayerId] = useState<number | null>(null)

👉 表示する選手IDを管理


② 表示データの分岐（核心）

const filteredConditions = selectedPlayerId === null
  ? conditions
  : conditions.filter((c) => c.playerId === selectedPlayerId)


③ 表示を変更

{filteredConditions.map((c) => (

👉 表示元を変更


④ 入力で選択できるようにする

<input
  type="number"
  placeholder="選手IDで絞る"
  onChange={(e) =>
    setSelectedPlayerId(
      e.target.value === "" ? null : Number(e.target.value)
    )
  }
/>



■ 重要理解（本質）

① 表示データは作ってから使う

👉 JSX内で処理しない
👉 事前に配列を作る


② 三項演算子
条件 ? A : B

👉 条件で表示内容を切り替える


③ filterの役割
conditions.filter((c) => 条件)

👉 条件に合うデータだけ残す


④ 状態によるUI制御

state変更 → 再描画

表示が自動で変わる


⑤ nullの意味

👉 「未選択状態」



■ データの流れ（完成形）

input（選手ID）
↓
selectedPlayerId更新
↓
filteredConditions生成
↓
mapで表示



■ 現在できること

・履歴一覧表示
・選手IDで絞り込み
・空入力で全表示