

Day30 追加処理（React）


1. 追加処理とは

Reactでは 配列のstateに新しいデータを追加する処理 を作る。


例

選手一覧

const [players, setPlayers] = useState<string[]>([])


入力フォーム

const [name, setName] = useState("")


2. Reactの重要ルール（イミュータブル）

Reactでは
stateを直接変更してはいけない

理由
Reactは
stateが新しい値になったか
で画面更新を判断するため。



3. ダメな書き方

players.push(name)
setPlayers(players)

理由

pushは元の配列を直接変更する

つまり

同じ配列

なのでReactが更新を検知できない可能性がある。



4. 正しい書き方

setPlayers([...players, name])

意味

...players

は スプレッド構文 で

配列の中身を展開する



5. 動作の流れ

元のstate

players = ["三笘", "久保"]


追加する値

name = "堂安"


処理

setPlayers([...players, name])


結果

["三笘", "久保", "堂安"]

つまり

新しい配列を作ってstate更新



6. React追加処理の本質

Reactでは

stateは直接変更しない

代わりに

新しい配列を作って更新する

これを

イミュータブル更新

という。



7. Day30で覚えるコード

setPlayers([...players, name])

意味

既存の配列 + 新しい要素
↓
新しい配列を作る
↓
state更新



Day30 核心

Reactの追加処理は
元の配列を変更せず、スプレッド構文で新しい配列を作ってstateを更新する。