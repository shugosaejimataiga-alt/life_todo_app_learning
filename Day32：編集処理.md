

Day32 編集処理（React）

Reactでは stateを直接変更せず、新しい配列を作って更新する（イミュータブル）。
編集処理は map() を使い、編集対象の index（editIndex）だけ新しい値に変更し、それ以外は元の要素をそのまま返すことで実現する。


編集処理の基本コード

const updatedPlayers = players.map((player, index) => {
  if (index === editIndex) {
    return newName
  } else {
    return player
  }
})

setPlayers(updatedPlayers)


処理の流れ

配列を1つずつ確認
↓
index === editIndex
→ 新しい値に変更

それ以外
→ 元の要素をそのまま返す
↓
新しい配列を作る
↓
setStateで更新



削除との違い

削除

要素数が減る
→ filter()


編集

要素数は変わらない
→ map()


例

元の配列

["三笘", "久保", "堂安"]

久保を編集

editIndex = 1
newName = "久保建英"

結果

["三笘", "久保建英", "堂安"]



覚えるポイント

Reactは stateを直接変更しない

編集 → map()

削除 → filter()

editIndex = 編集する配列の番号