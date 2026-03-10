

Day11：Union型（完全復習）


Union型は
「この型 または この型」のように 複数の型のどれかを許可する型。


書き方

type 型名 = 型A | 型B | 型C

意味
A または B または C


例

ポジション
type Position = "GK" | "DF" | "MF" | "FW"

利き足
type Foot = "右" | "左" | "両足"

怪我レベル
type InjuryLevel = "none" | "light" | "serious"

RPE
type RPE = 1 | 2 | 3 | 4 | 5


重要ルール

文字列の場合

type Position = "GK" | "DF" | "MF" | "FW"

→ ""が必要

理由
文字列だから



数字の場合

type RPE = 1 | 2 | 3 | 4 | 5

→ ""は不要

理由
number型だから



間違い例

type Foot = 右 | 左 | 両足

理由

右
左
両足

が 変数として扱われてしまう



Union型の目的

入れていい値を制限する

例

let position: Position = "GK"   // OK
let position: Position = "Coach" // エラー

覚える核心
Union型 = 「この中のどれか」
type 型名 = 型A | 型B | 型C