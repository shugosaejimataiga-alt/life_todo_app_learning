

Day42：バリデーション 完全まとめ


■ 目的

👉 不正な入力を防ぐこと

空の名前で登録されないようにする

データの質を保つ



■ 実装したこと

① バリデーションの導入

function validateForm() {
  if(form.name.trim() === "") {
    alert("名前を入力してください")
    return false
  }
  return true
}

👉 入力が正しいかを判定する関数を作成


② trimの使用

form.name.trim() === ""

👉 スペースだけの入力も防ぐ


③ 処理の前にチェック

if(!validateForm()) return

👉 ダメな場合は処理を止める


④ 共通化

addPlayer にも
updatePlayer にも

👉 同じチェックを使い回し


⑤ 処理と判定の分離

validateForm → 判定
add/update → 処理

👉 役割を分けた設計


⑥ UX改善（フォームリセット）

setForm({
  name: "",
  position: "GK"
})

👉 登録後に入力を初期化



■ コード構造の理解（重要）

現在の役割

players → データ本体

form → 入力中データ

editingPlayer → 編集対象

👉 状態管理が完全に分離されている



■ 本質理解

① バリデーションとは

👉 「データを作る前に止める仕組み」


② return true / false の意味

true → OK（処理続行）
false → NG（処理停止）


③ この1行の意味

if(!validateForm()) return

👉 「ダメなら即終了」


④ 設計の本質

👉 1つの関数は1つの役割

validateForm → 判定だけ
add/update → 処理だけ



■ 到達レベル

CRUD完成

フォーム設計理解

バリデーション実装

ロジック分離理解

👉 実務レベルの基礎に到達



■ 一言で

👉 「入力チェックを関数化し、処理と分離して安全にデータを扱えるようにした」