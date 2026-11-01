# satapura-web

サタプラ検索の iPhone ホーム画面用ページ（GitHub Pages）。
本体（GAS）は非公開リポジトリ `fkmkzyk/satapura_ranking` で管理しており、ここにはその `docs/` の中身をコピーしています。
データは GAS の Web アプリ API（`?api=rankings`）から取得します。

公開URL: https://fkmkzyk.github.io/satapura-web/

## できること

- 商品名・メーカー・テーマでのリアルタイム検索（「1位のみ」「サタデミー賞」などの絞り込みチップ付き）
- 商品名から Google 検索、最新12回分は放送日から MBS 公式ページへ移動
- 前回のデータを端末に保存して即時表示し、裏で最新データを取得
- 新しい版を公開すると自動で読み込み直す（右上の更新ボタンで手動更新も可能）

AIチャットは削除済みで、検索のみの画面です。

## ホーム画面への追加

iPhone の Safari で公開URLを開き、共有 ＞「ホーム画面に追加」を選びます。以前に GAS の URL を追加していた場合は、そのアイコンを削除してから追加し直してください。

## 更新のしかた

- このリポジトリのファイルは直接編集せず、`satapura_ranking` の `docs/` を変更してから同じ内容をここにコピーします。
- 画面を変えたときは `index.html` の `APP_VERSION` を上げます。アイコンを差し替えたときは `?v=` の数字も上げます。
- GAS を新しい URL で再デプロイした場合は `index.html` の `GAS_API_URL` を書き換えます（通常は既存デプロイを「新バージョン」で更新すれば URL は変わりません）。
- Pages の設定: Settings ＞ Pages で Source を `Deploy from a branch`、Branch を `main` / `/ (root)`。
