
Day4 完全まとめ（見返し用）

オブジェクト
→ 「名前 : 値」のデータ


例

{
  title: "世界一周"
}

TypeScriptのオブジェクト型

{
  title: string
}

意味

title という 名前のデータ
値は string型



複数プロパティ

{
  title: string
  likes: number
}

意味

title → string
likes → number



型エラー例

{
  title: 100
}

理由

title は string型
100 は number型



正しい例

{
  title: "100"
}

