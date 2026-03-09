
Day9：関数の型（TypeScript）


関数の型 = 引数の型 + 戻り値の型

function add(a: number, b: number): number {
  return a + b
}



戻り値がない場合は void

function logMessage(message: string): void {
  console.log(message)
}



比較結果は boolean（true / false）

function isAdult(age: number): boolean {
  return age >= 18
}