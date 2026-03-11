

Day17 型設計練習（Physical）


1. 目的

サッカー選手の フィジカルデータを保存する型（Physical型） を設計する。



2. 保存するデータ

Physicalログには次の情報が必要になる。

どの選手のデータか

体重

体脂肪

50m走タイム

ジャンプ力

記録日



3. 型の決定理由

playerId
選手を識別するためのID
数字で管理するため number

weight
体重は増減や比較をするデータ
計算できる必要があるため number

bodyFat
体脂肪率
数値データなので number

sprint50m
50m走タイム
数値データなので number

jump
ジャンプ力
数値データなので number

date
"2026-03-11" のように扱う
文字列で保存するため string



4. Physical型

type Physical = {
  playerId: number
  weight: number
  bodyFat: number
  sprint50m: number
  jump: number
  date: string
}


5. Physicalログの構造イメージ

選手ID + フィジカル数値 + 記録日

例

playerId: 10
weight: 72
bodyFat: 12
sprint50m: 6.3
jump: 55
date: "2026-03-11"



6. この型を作る理由

TypeScriptでは
データの形（構造）を最初に決めることで

データのミスを防ぐ

型エラーでバグを防ぐ

アプリ設計を明確にする



7. 今日の本質

Day17は

「フィジカル記録を保存するデータ構造をTypeScriptで設計する」

学習だった。


