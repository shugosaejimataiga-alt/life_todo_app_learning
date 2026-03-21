

Day53.5 完全まとめ

■ 今日やったこと

Conditionにバリデーションを実装し、
👉 不正な入力を保存できない仕組みを作成



■ 実装内容

① バリデーション関数作成

function validateCondition() {
  if (conditionForm.playerId === 0) {
    setError("選手IDを入力してください")
    return false
  }
  if (conditionForm.date === "") {
    setError("日付を入力してください")
    return false
  }
  if (conditionForm.condition === "") {
    setError("体調を入力してください")
    return false
  }
  if (conditionForm.rpe === 0) {
    setError("RPEを入力してください")
    return false
  }
  setError("")
  return true
}

👉 入力チェック＋エラーメッセージ設定


② 保存前にチェック

if (!validateCondition()) {
  return
}

👉 NGなら処理停止


③ エラー表示
{error && <p style={{ color: "red" }}>{error}</p>}

👉 エラーがある時だけ表示


④ 成功時のリセット
setError("")

👉 正常保存後にエラー消去



■ 重要理解（本質）

① validateの役割
true → 保存OK
false → 保存NG

② !（否定）
!validateCondition()

👉 ダメなときにtrueになる

③ 処理の流れ
入力 → validate → NGなら停止 → OKなら保存

④ Reactの状態管理
error → UI表示制御
state変更 → 自動再描画



■ 到達レベル

バリデーション
UI連動
処理制御

すべて揃っている状態

これでDay53.5は完全に再現可能な状態。