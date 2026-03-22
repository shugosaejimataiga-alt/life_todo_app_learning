

Day56 完全まとめ（Match型設計）


■ 今日やったこと

● Match（試合）のデータ構造を設計

試合に必要な情報を定義した

id：試合識別
date：日付
opponent：対戦相手
type：試合種類
status：試合状態
goalsFor：得点
goalsAgainst：失点


● union型を導入

typeを固定化した

"league"
"cup"
"training"
"event"

statusも固定

"scheduled"
"finished"

👉 不正な値を防ぐため



● useStateで管理開始

const [matches, setMatches] = useState<Match[]>([])

👉 試合データを配列で管理する準備



● 新しい画面ファイルを作成

Matches.tsx を作成

👉 機能ごとにファイル分離



■ 学んだこと（本質）

● 「型 = 設計図」

👉 データの形を最初に決めることでバグを防ぐ


● union型の意味

👉 値を制限することで安全な設計になる


● useState<型[]>

👉 「その型だけを持つ配列」を保証する


● 設計の順番

👉 UIより先にデータ設計



■ 今の到達点

👉 「試合（Match）」という概念をアプリに追加した

👉 これから

Stat（成績）
Tactic（戦術）
Condition（コンディション）

すべてが

👉 Matchに紐づく設計の土台が完成



■ 一言で

👉 「試合を中心にしたデータ設計を作った日」