
Day10：戻り値の型（完全復習まとめ）


1. 戻り値とは

関数は 処理した結果を外に返すことができる。
この 返される結果 を 戻り値（return value） という。

例

function add(a:number,b:number){
 return a+b
}

この関数は

5 + 3 → 8

という 結果を返す。



2. 戻り値の型

TypeScriptでは
関数が返す値の型を明示する。


書き方

function 関数名(引数):戻り値の型


例

function add(a:number,b:number):number{
 return a+b
}

意味
この関数は number を返す


3. string を返す関数


function greet(name:string):string{
 return "Hello " + name
}

意味
戻り値は string


4. 戻り値がない場合

何も返さない関数は
void
を書く。

例

function logMessage(text:string):void{
 console.log(text)
}

意味
出力するだけ  
値は返さない


5. 今日の最重要ポイント

関数の型は

function 名前(引数):戻り値の型

例

(a:number):number
(name:string):string
():void


6. 覚えるべき核心

TypeScriptでは

引数の型
+
戻り値の型

この 2つを必ず決める。


Day10：戻り値の型を学びました。