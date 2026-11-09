# satapura-web

サタプラ検索の iPhone ホーム画面用ページ（GitHub Pages）。
本体（GAS・検索 API）は非公開リポジトリ `fkmkzyk/satapura_ranking` で管理しており、ここにはその `docs/` の中身をコピーしています。
検索は Cloudflare の検索 API（https://satapura-search.fkmkzyk.workers.dev）で行い、一致した分（最大30件）だけを受け取ります。

公開URL: https://fkmkzyk.github.io/satapura-web/

## できること

- 商品名・メーカー・テーマでのリアルタイム検索（「1位のみ」「サタデミー賞」などの絞り込みチップ付き）
- 商品名から Google 検索、最新12回分は放送日から MBS 公式ページへ移動
- 前回表示した最新30件を端末に保存して即時表示し、裏で最新を取り直す
- 新しい版を公開すると自動で読み込み直す（右上の更新ボタンで手動更新も可能）

AIチャットは削除済みで、検索のみの画面です。

## 非公式表示・プライバシー

- ページ下部に「非公式・MBS／番組とは無関係」の表示と、MBS公式サイトへの出典リンクを載せています。
- 掲載中止のご依頼やお問い合わせは、このリポジトリの [Issues](https://github.com/fkmkzyk/satapura-web/issues) で受け付けています。
- プライバシーポリシー: [privacy.html](https://fkmkzyk.github.io/satapura-web/privacy.html)（Google アナリティクス、検索語の検索サーバーへの送信、端末への保存について）

## ホーム画面への追加

iPhone の Safari で公開URLを開き、共有 ＞「ホーム画面に追加」を選びます。以前に GAS の URL を追加していた場合は、そのアイコンを削除してから追加し直してください。

## 更新のしかた

- このリポジトリのファイルは直接編集せず、`satapura_ranking` の `docs/` を変更してから同じ内容をここにコピーします。
- 画面を変えたときは `index.html` の `APP_VERSION` を上げます。アイコンを差し替えたときは `?v=` の数字も上げます。
- 検索 API の URL は `index.html` の `SEARCH_API_URL` です。Cloudflare の Worker（`satapura-search`）の URL が変わった場合だけ書き換えます。検索データは GAS が毎週 Cloudflare に送るため、このリポジトリの更新は不要です。
- Pages の設定: Settings ＞ Pages で Source を `Deploy from a branch`、Branch を `main` / `/ (root)`。
