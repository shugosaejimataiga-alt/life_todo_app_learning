

Day52 完全まとめ（履歴表示）


■ 今日やったこと

Conditionデータを
保存 → 画面に一覧表示（履歴）する流れを完成



■ 全体の流れ（最重要）
入力
↓
conditionForm更新（onChange）
↓
保存クリック
↓
addCondition実行
↓
conditions配列に追加
↓
mapで画面表示


■ 核となるコード構造

① 保存（データ生成）
const newCondition = {
  id: Date.now(),
  ...conditionForm
}

👉 入力データ → 完成データへ変換


② 配列追加（最重要）
setConditions([...conditions, newCondition])

👉 新しい配列を作って追加（イミュータブル）


③ 表示（今回の核心）
{conditions.map((c) => (
  <div key={c.id}>
    <p>
      日付：{c.date} / 体調：{c.condition} / RPE：{c.rpe}
    </p>
  </div>
))}



■ 本質理解（重要ポイント）

① 状態の分離
conditionForm → 入力中
conditions → 保存済み

👉 一時データと確定データは別物


② mapの正体
配列 → UIに変換する仕組み

👉 データが増える = 自動で表示も増える


③ Reactのルール
returnの中しか画面に出ない

👉 JSXはすべてreturn内に書く


④ UI設計
1データ = 1行で表示

👉 情報はまとまりで扱う



■ 現在の完成状態
入力 → 保存 → 表示
が一連で動く