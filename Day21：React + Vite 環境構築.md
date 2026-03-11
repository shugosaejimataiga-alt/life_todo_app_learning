

Day21
React + Vite 環境構築



① Reactプロジェクト作成

コマンド

npm create vite@latest soccer-app

意味
Reactアプリの プロジェクト雛形（設計図）を作成

選択
Framework → React
Variant → TypeScript
Vite beta → No



② プロジェクトフォルダへ移動

cd soccer-app

意味
作成された Reactプロジェクトフォルダに移動



③ ライブラリインストール

npm install

意味
package.json を読む
必要なライブラリをダウンロード
node_modules フォルダ作成

ライブラリ例

react
react-dom
vite
typescript



④ 開発サーバー起動

npm run dev

意味
Vite開発サーバー起動
Reactアプリをブラウザ表示

URL
http://localhost:5173



⑤ VSCodeでプロジェクトを開く

code .

意味
現在のフォルダ（soccer-app）を VSCodeで開く



⑥ Reactプロジェクト構造

soccer-app
 ├ node_modules
 ├ public
 ├ src
 ├ package.json
 ├ vite.config.ts
 └ index.html


役割

node_modules
→ ライブラリ保存フォルダ

src
→ Reactコードを書く場所




⑦ Reactの基本構造

main.tsx
   ↓
App.tsx
   ↓
ブラウザ表示

main.tsx
→ Reactアプリ起動

App.tsx
→ 画面コンポーネント



Day21 要点

Vite → React開発環境ツール
npm install → ライブラリインストール
npm run dev → 開発サーバー起動
src → Reactコードを書く場所
App.tsx → 画面コンポーネント


Day21：React + Vite 環境構築