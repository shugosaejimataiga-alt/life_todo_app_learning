

Day18 型設計練習（Tactic）


1. 現実の構造を分解する

サッカー戦術は次の構造になっている。

戦術
↓
シーン（フレーム）
↓
選手とボール
↓
座標

この構造を TypeScriptの型に変換する。



2. 座標（Position）

ピッチ上の位置は x座標とy座標で表す。

type Position = {
  x: number
  y: number
}

意味

1つの位置

例

{x:120, y:300}


3. 戦術の1シーン（TacticFrame）

1つの戦術シーンは

選手の位置

ボールの位置

で構成される。

type TacticFrame = {
  players: Position[]
  ball: Position
}

意味

players → 選手（複数）
ball → ボール（1つ）



4. 戦術全体（Tactic）

戦術は 複数のシーンの集合。

type Tactic = TacticFrame[]

意味

1コマ目
2コマ目
3コマ目



5. データ構造
Tactic
 └ TacticFrame[]
      ├ players: Position[]
      │     ├ Position
      │     ├ Position
      │     └ Position
      └ ball: Position



6. 配列とオブジェクトの判断

配列
同じものが並ぶ

例
players[]
frames[]
オブジェクト

役割が違う

例
from / to
left / right
ball / players



7. 型設計の本質

アプリ設計とは

現実
↓
構造を理解
↓
データ構造に変換
↓
型で表現

することである。




Day18で作った最終コード

type Position = {
  x: number
  y: number
}

type TacticFrame = {
  players: Position[]
  ball: Position
}

type Tactic = {
  TacticFrame[]
}




Day18の核心

戦術データは

座標
↓
フレーム
↓
戦術

という 階層構造のデータとして設計する。


