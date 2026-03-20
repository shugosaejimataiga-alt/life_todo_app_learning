

✅ Day46まとめ（完全版）

今日はCondition（コンディション）の設計を行った。

まず、コンディション管理で必要な情報を整理した。
「どの選手か（playerId）」「日付（date）」「体調（condition）」「RPE（運動強度）」を記録する必要があると定義した。

そのうえで、これらをまとめた**Condition型（データの設計図）**を作成した。

type Condition = {
  id: number
  playerId: number
  date: string
  condition: string
  rpe: number
}

この型は「1人の選手の1日の状態」を表すものであり、Playerとは役割が異なるデータである。

重要な理解として、

型は「データの形」を決めるもの
フォームや処理とは別物
設計 → 実装の順で進める

という構造を明確にした。

また、Player管理と同様に、Conditionも最終的にはCRUD（追加・削除・編集）で扱うデータになるが、今日はそこには進まず、あくまで設計のみで止めることが正しい進め方であると理解した。