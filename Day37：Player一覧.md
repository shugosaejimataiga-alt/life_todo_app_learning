

Day37：Player一覧表示（React）



1. Player型（選手1人のデータ構造）

type Player = {
  id: number
  name: string
  position: "GK" | "DF" | "MF" | "FW"
}

型は データのルール

"GK" | "DF" | "MF" | "FW" は Union型

不正な値を防ぐ（例："AAA" はエラー）



2. Player配列

const players: Player[] = [
 { id:1, name:"三笘", position:"MF" },
 { id:2, name:"堂安", position:"MF" },
 { id:3, name:"久保", position:"FW" }
]

意味

Player[] = Player型オブジェクトの配列

Player → 選手1人

Player[] → 選手のリスト



3. map()で一覧表示

{players.map((player) => (
  <div key={player.id}>
    {player.name} - {player.position}
  </div>
))}

意味

配列データ → UIに変換

player は 配列の1要素

Reactでは 配列表示にmap()を使う



4. keyの役割

key={player.id}

意味

Reactが要素を識別するため

理由

追加
削除
並び替え

のときに どの要素か判断するため

最適

id（ユニークな値）



5. JSXは1つの要素で返す

NG

return (
  <h1>Hello</h1>
  <p>World</p>
)


OK

<div>
  <h1>Hello</h1>
  <p>World</p>
</div>

または

<>
  <h1>Hello</h1>
  <p>World</p>
</>



6. Fragment

<>
</>

役割
要素をまとめる

特徴
HTMLに出力されない


例

JSX
<>
  <h1>
  <p>
</>

HTML
<h1>
<p>



7. useState（Reactの状態管理）

const [players, setPlayers] = useState<Player[]>([])

意味

players → 現在のデータ
setPlayers → データ更新関数
Player[] → Player型の配列
[] → 初期値（空配列）



8. Reactの重要ルール（イミュータブル）

NG

players.push(newPlayer)


理由

元の配列を変更するとReactが検知できない


OK

setPlayers([...players, newPlayer])


意味

元の配列をコピー
+
新しいデータ追加
=
新しい配列



Day37の核心
データ（Player配列）
↓
map()
↓
React UI（一覧表示）

つまり

データ → 画面

を作る仕組みを理解した。