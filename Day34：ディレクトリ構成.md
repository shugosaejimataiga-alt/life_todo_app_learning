

Day34 ディレクトリ構成（React）

Reactではアプリが大きくなると、すべてを App.tsx に書くとコードが巨大になり管理できなくなる。そのため コンポーネントごとにファイルを分けて整理する。


基本構成

src
 ├ App.tsx
 ├ components
 │   ├ Header.tsx
 │   ├ PlayerList.tsx
 │   └ PlayerForm.tsx


重要ルール

1コンポーネント = 1ファイル

コンポーネント名・ファイル名は大文字スタート

UIコンポーネントは components フォルダに入れる

コンポーネントを使うときは importする。


例

import PlayerList from "./components/PlayerList"
import PlayerForm from "./components/PlayerForm"

拡張子 .tsx は通常書かなくてもよい。
Reactは自動で .ts .tsx .js .jsx を探す。



本質

Reactアプリは

「コンポーネントを分割 → フォルダで整理 → importして組み立てる」

この構造で作る。