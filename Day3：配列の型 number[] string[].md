

Day3：配列の型

配列 = 複数のデータをまとめる箱

TypeScriptでは
配列の型は「型[]」で書く

型[]


例

number[]   → 数字の配列
string[]   → 文字の配列
boolean[]  → true / false の配列



コード例

const scores: number[] = [10,20,30]

const names: string[] = ["taro","hanako"]

const doneList: boolean[] = [true,false,true]


重要ポイント

string   → 文字1つ
string[] → 文字の配列

つまり

配列の型 = 中身の型 + []