

Day38まとめ

Player追加（React State / 入力 / 配列追加）



1 Reactのstate（データ保存）

const [players, setPlayers] = useState<player[]>([])


意味

players
→ 選手データを保存する配列

setPlayers
→ playersを更新する関数


型
players : player[]

つまり

playerオブジェクトの配列



2 player型

type player = {
  id: number
  name: string
  position: "GK" | "DF" | "MF" | "FW"
}


意味

選手データの設計図


例

{
 id: 1
 name: "三笘"
 position: "MF"
}



3 入力フォーム

<input
 placeholder="名前"
 onChange={(e)=>setName(e.target.value)}
/>


意味

入力
↓
onChange
↓
setName
↓
name state更新

保存されるところが
name



4 select入力

<select onChange={(e)=>setPosition(e.target.value as "GK" | "DF" | "MF" | "FW")}>


意味

ポジション選択
↓
setPosition
↓
position state更新



5 Reactの仕組み（重要）

setState
↓
state更新
↓
Reactが再レンダリング
↓
コンポーネント再実行
↓
UI更新



6 選手追加ボタン

<button onClick={addPlayer}>


意味

クリック
↓
addPlayer関数実行



7 addPlayer関数

function addPlayer(){

 const newPlayer = {
  id: Date.now(),
  name: name,
  position: position
 }

 setPlayers([...players, newPlayer])

}


流れ

name state
position state
↓
newPlayer作成
↓
players配列に追加
↓
state更新
↓
再レンダリング




8 配列追加

setPlayers([...players, newPlayer])


意味

既存配列
+
新しい要素


結果

players = [
 player1
 player2
 player3
]



9 players表示

players.map((player)=>(
 <div key={player.id}>
  {player.name} - {player.position}
 </div>
))


意味

players配列
↓
map
↓
1人ずつ取り出す
↓
UI作成


例

三笘 - MF
久保 - FW



10 Reactの全体の流れ

① 名前入力
↓
setName

② ポジション選択
↓
setPosition

③ 選手追加クリック
↓
addPlayer

④ newPlayer作成
↓
setPlayers

⑤ players更新
↓
React再レンダリング

⑥ players.map
↓
UI表示



11 idについて

id: Date.now()


意味
現在時刻をIDにする


理由
重複しないID

※後でLaravel + MySQLになると

DBがIDを作る



Day38の核心

入力
↓
state保存
↓
ボタン
↓
配列追加
↓
map表示



Day38で理解するべきReact
useState
setState
入力イベント
クリックイベント
配列更新
map表示

これで Player追加機能完成です。