

Day39 Player削除（完全まとめ）


今日作った機能

Player削除機能
選手一覧から特定の選手を削除できるようにした。



削除機能の流れ

削除ボタン
↓
onClick発動
↓
deletePlayer(player.id) 実行
↓
filter で削除対象以外を残す
↓
新しい配列作成
↓
setPlayers にセット
↓
React再レンダリング
↓
画面から選手が消える



削除関数

function deletePlayer(id:number){

 const newPlayers = players.filter((player)=>player.id !== id)

 setPlayers(newPlayers)

}

処理の意味


id受け取り

deletePlayer(player.id)

クリックされた選手の id が関数に渡される。



filter処理

players.filter((player)=>player.id !== id)

意味
players配列を 1人ずつ確認する



判定
player.id !== id


評価
true  → 残す
false → 削除


例
players

1 三笘
2 久保
3 堂安

久保削除

id = 2


判定

1 !== 2 → true → 残る
2 !== 2 → false → 削除
3 !== 2 → true → 残る



結果

newPlayers

1 三笘
3 堂安



削除ボタン

<button onClick={()=>deletePlayer(player.id)}>
削除
</button>



()=> の意味

()=>deletePlayer(player.id)

意味

クリックされたときに
deletePlayer(player.id)を実行する関数
なぜ関数で包むのか

もし

onClick={deletePlayer(player.id)}

にすると

画面表示時に削除が実行される

ため、クリック時に実行するため 関数で包む。




React削除の基本パターン

配列を直接変更しない
↓
filterで新しい配列作る
↓
setState
↓
React再レンダリング



今日理解したReact
onClick
filter
配列削除
setState更新
React再レンダリング
イベント→state更新→UI更新



今日完成したコード（重要部分）

function deletePlayer(id:number){

 const newPlayers = players.filter((player)=>player.id !== id)

 setPlayers(newPlayers)

}
{players.map((player)=>(
 <div key={player.id}>
  {player.name} - {player.position}

  <button onClick={()=>deletePlayer(player.id)}>
   削除
  </button>

 </div>
))}



Day39の成果

Player追加
Player一覧表示
Player削除

これで 基本CRUDのDeleteが完成。