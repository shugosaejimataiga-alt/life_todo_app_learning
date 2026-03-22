

Day57 完全まとめ（ルーティング導入）
■ 今日やったこと
● ルーティングの導入

react-router-dom をインストールし、
URLによって画面を切り替える仕組みを構築した

● BrowserRouter設定

App.tsxでアプリ全体をBrowserRouterで包んだ

👉 URL監視を有効化
👉 ルーティングの土台を作成

● Route定義（画面対応表）
<Routes>
  <Route path="/players" element={<Players />} />
  <Route path="/matches" element={<Matches />} />
  <Route path="/match/create" element={<MatchCreate />} />
  <Route path="/match/:id" element={<MatchDetail />} />
</Routes>

👉 URLごとに表示画面を定義

● トップURL制御
<Route path="/" element={<Navigate to="/players" />} />

👉 / にアクセスしたら /players に遷移

● 動的ルート理解
/match/:id

👉 試合ごとにURLを変える仕組み
👉 /match/1 /match/2 など

● ページ構成の設計
src → ページ（画面）
components → 部品

新規作成：

MatchCreate.tsx
MatchDetail.tsx
● 動作確認

URL直接入力で確認：

/players
/matches
/match/create
/match/1

👉 すべて正常表示

■ 学んだこと（本質）
● ルーティングの役割

👉 URL = 今どの画面かを表す

● Reactの進化

今まで：
👉 1画面アプリ

これから：
👉 複数画面アプリ

● BrowserRouterの意味

👉 ルーティングを有効にする箱

● Routes / Routeの意味

👉 URLと画面の対応表

● Navigateの意味

👉 自動リダイレクト

● :idの意味

👉 可変値（動的ルート）