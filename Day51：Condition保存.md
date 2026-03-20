

Day51 完全整理（Condition保存）


■ 今日やったこと

Condition入力データを「保存」できるようにし、保存後にフォームを初期化する処理を実装



■ 本質理解

① stateの役割の分離

conditionForm → 入力中の一時データ
conditions → 保存されたデータ

👉 「編集中」と「保存済み」を完全に分けている



② 保存の正体

const newCondition = {
  id: Date.now(),
  ...conditionForm
}

👉 入力中データを「1つの完成データ」に変換


③ 配列追加（最重要）

setConditions([...conditions, newCondition])

既存データをコピー
新しいデータを追加

👉 元の配列は変更しない（イミュータブル）


④ フォーム初期化

setConditionForm({
  playerId: 0,
  date: "",
  condition: "",
  rpe: 0
})

👉 保存後に入力状態をリセット
👉 次の入力をスムーズにする



■ データの流れ（完成形）

入力
↓
onChange
↓
conditionForm更新
↓
保存クリック
↓
addCondition
↓
newCondition生成
↓
conditionsに追加
↓
フォーム初期化



■ Reactの重要理解

inputのvalueはstateで制御される

stateが変わると画面が更新される

オブジェクトは丸ごと更新する

配列は新しく作る