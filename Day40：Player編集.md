

Day40まとめ（Player編集）


■ 目的
既存のPlayerデータを変更（Update）できるようにする


■ 全体の流れ（最重要）

① 編集ボタン押す
↓
② editingPlayerに対象playerを入れる
↓
③ useEffectでフォームに値をコピー
↓
④ 入力内容を変更
↓
⑤ 保存ボタン押す
↓
⑥ mapで該当playerだけ更新
↓
⑦ setPlayersで配列を置き換え
↓
⑧ 再描画
↓
⑨ editingPlayerをnullに戻す



■ 状態（state）の役割整理

players → 本体データ（画面の正体）
name → フォーム入力（編集用）
position → フォーム入力（編集用）
editingPlayer → 今どのplayerを編集しているか



■ 重要な理解

① 本体はすぐに変更しない
編集ボタンを押した時点では
playersは変わらない
② 編集は「コピーしてから変更」
editingPlayer → name / position にコピー
↓
フォームで編集
③ 保存時に初めて本体を変更
setPlayersで配列ごと更新



■ useEffectの役割

editingPlayerが変わったとき
↓
フォーム（name, position）に値を入れる
一行
useEffect = 状態の変化に反応して処理する



■ updatePlayerの本質

mapで配列を回す
↓
編集対象だけ新しく作る
↓
それ以外はそのまま
↓
新しい配列にする


コードの意味

players.map((player)=>{
  if(player.id === editingPlayer.id){
    return { ...player, name, position }
  }
  return player
})


一行
該当データだけ新しく作り直す



■ イミュータブル理解

元のデータは変更しない
↓
新しいオブジェクトを作る
↓
新しい配列を作る
↓
丸ごと置き換える

一行
変更ではなく「作り直して差し替え」



■ valueの理解（重要）

valueを付けると
inputの中身 = state

違い
valueなし → inputとstateが別（ズレる）
valueあり → 完全同期



■ editingPlayer && の意味

editingPlayerがあるときだけ表示



■ 今回の本質

編集とは
「本体を直接変える」のではなく

①選択
②コピー
③編集
④保存
⑤置き換え

の流れで行う



■ 完成状態
Create → 追加
Read → 表示
Delete → 削除
Update → 編集

CRUD完成


■ 一番重要な一文
Reactは「状態をどう設計するか」で全てが決まる

これがDay40の完全理解です。