
■ Day47 完全まとめ（Condition入力フォーム）

■ 今日やったこと

Condition（コンディション）を入力して保存する仕組みを作った



■ 全体の流れ（最重要）
① 入力用stateを作る（conditionForm）
② 入力UI（ConditionForm）を作る
③ 親 → 子にpropsで渡す
④ 子で入力をstateに反映
⑤ 保存ボタンでconditionsに追加


■ 状態の役割（超重要）
conditionForm = 入力中のデータ（下書き）
conditions = 保存されたデータ（一覧）


■ 親と子の関係
親（Condition.tsx）
→ stateと関数を持つ

子（ConditionForm.tsx）
→ propsで受け取って使うだけ


■ propsの本質
props = 親から子への受け渡し


■ 実際に渡しているもの
conditionForm → 値を見るため
setConditionForm → 入力で更新するため
addCondition → 保存処理を実行するため


■ データの流れ
入力
↓
props.setConditionForm（子）
↓
親のstate更新
↓
保存ボタン
↓
props.addCondition（子）
↓
親のaddCondition実行
↓
conditionsに追加


■ 技術的ポイント

● value + onChange
入力とstateを同期する仕組み

● スプレッド構文
...conditionForm
→ 他の値を消さずに更新する

● setStateの型
React.Dispatch<React.SetStateAction<〇〇>>
→ state更新関数の型（お決まり）

● addConditionの型
() => void
→ 引数なし・戻り値なしの関数


■ 一番重要な理解
親が持つ → 子に渡す → 子が使う → 親が更新する


■ 今日の到達点
入力 → state反映 → 保存 → 配列に追加

👉 CRUDの「Create」が完成