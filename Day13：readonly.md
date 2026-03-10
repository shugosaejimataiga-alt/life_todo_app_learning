
Day13：readonly

readonly は 読み取り専用プロパティを作る。オブジェクト作成後は値を変更できない。
readonly が付いたプロパティだけ変更禁止で、付いていないプロパティは変更できる。

例

type Player = {
  readonly id: number
  name: string
}

const p: Player = {
  id: 1,
  name: "Messi"
}

p.name = "Ronaldo" // OK
p.id = 2           // エラー

