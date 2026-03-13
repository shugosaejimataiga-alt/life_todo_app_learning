

Day31 削除処理（React）


1. mapで配列を表示

map() は配列を1つずつ取り出す。

players.map((player, index) => (
  <div key={index}>
    {player}
    <button onClick={() => deletePlayer(index)}>削除</button>
  </div>
))

意味

player → 配列の中身
index → 配列の番号

例

["三笘","久保","堂安"]

player="三笘" index=0
player="久保" index=1
player="堂安" index=2



2. 削除ボタンを押す

onClick={() => deletePlayer(index)}


例

堂安の削除ボタン
↓
deletePlayer(2)



3. 削除関数

const deletePlayer = (deleteIndex: number) => {

意味
deleteIndex に削除したい index が入る


例

deletePlayer(2)
↓
deleteIndex = 2



4. filterで削除

const newPlayers =
players.filter((player,index)=>index !== deleteIndex)

意味
index が deleteIndex と違うものだけ残す


filterのルール

true  → 残る
false → 消える


例

players = ["三笘","久保","堂安"]
deleteIndex = 1


判定

0 !== 1 → true  → 三笘 残る
1 !== 1 → false → 久保 消える
2 !== 1 → true  → 堂安 残る


結果

["三笘","堂安"]



5. state更新

setPlayers(newPlayers)

流れ

新しい配列を作る
↓
setState
↓
Reactが再描画



Reactの重要ルール

Reactでは

stateを直接変更しない

なので

❌ NG
players.splice()


⭕ 正しい
filterで新しい配列を作る
setStateで更新

これを イミュータブル更新 という。



削除処理の全体コード

const deletePlayer = (deleteIndex: number) => {
  const newPlayers =
    players.filter((player,index)=>index !== deleteIndex)

  setPlayers(newPlayers)
}

players.map((player,index)=>(
  <div key={index}>
    {player}
    <button onClick={()=>deletePlayer(index)}>
      削除
    </button>
  </div>
))



Day31の核心（最重要）

削除処理 =
filterで削除後の新しい配列を作る
↓
setStateで更新
↓
Reactが再描画