

■ Day58 完全まとめ


● やったこと
Matches.tsx にダミーの試合データを追加
map() を使って試合一覧を表示
key={match.id} で各要素を識別
date / opponent をUIに表示
カード形式のUIを作成（border / padding / margin）
flex + column で縦並びレイアウトを実装


● 学んだこと（本質）


① mapの役割

配列のデータを「繰り返してUIに変換する」

👉 データ → 画面表示の基本構造



② keyの意味

Reactが「どの要素か」を識別するためのID

👉 再描画のズレ防止



③ UIは「表示したものしか出ない」

<p>{match.date}</p>
<p>vs {match.opponent}</p>

👉 書いていないデータは表示されない
（goalsForなどは意図的に出していない）



④ flex + column の意味

display: "flex"
flexDirection: "column"

👉 要素を縦に並べる



⑤ paddingの意味

padding: "16px"

👉 画面の余白（見やすさ）



● 今のコードの状態

試合データを持っている（state）
それをmapで表示できる
カードUIで縦に並ぶ

👉 一覧画面の土台完成


● 重要理解

id → 表示用ではなく内部識別
goals → Day63で扱う（今は出さない）
今は「UIだけ」を作るフェーズ