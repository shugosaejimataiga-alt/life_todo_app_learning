

Day50 学習まとめ（完全理解用）


■ 今日やったこと

Condition入力フォームにおいて
日付入力（date）を正しく扱える状態にした



■ 実装の本質

<input
  type="date"
  value={props.conditionForm.date}
  onChange={(e)=>
    props.setConditionForm({
      ...props.conditionForm,
      date: e.target.value
    })
  }
/>


■ 何をしているのか（本質）
① value
👉 stateの値を画面に表示

② onChange
👉 入力された値でstateを更新

③ 結果
👉 入力とstateが完全に一致する



■ オブジェクト更新の理解
{
  ...props.conditionForm,
  date: e.target.value
}

他の値（rpe / condition）を維持

dateだけ変更

👉 オブジェクトは毎回「丸ごと作り直す」



■ データ構造の理解
conditionForm
👉 入力中のデータ（編集中）

conditions
👉 保存済みデータ（履歴）



■ データの流れ

入力
↓
onChange
↓
setConditionForm
↓
state更新
↓
保存ボタン
↓
addCondition
↓
conditionsに追加



■ 今日の一番重要な理解

👉 inputはただの見た目ではない

valueでstateを表示し
onChangeでstateを変える

👉 Reactでは「stateが本体」



■ さらに重要な理解

👉 dateはデータの軸になる

いつの記録かを決める

今後すべての処理（履歴・グラフ）の基準になる