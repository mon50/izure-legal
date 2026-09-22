# izure-legal

Izure アプリの法的情報（プライバシーポリシー / 利用規約 / 特定商取引法に基づく表記）を
GitHub Pages で公開するための静的サイト。

正本は本体リポジトリ `tsumu`（private）の `docs/` 配下にあり、このリポジトリの
`index.html` と `legal/` はそこから写したもの。**このリポジトリを直接編集しない。**

旧 `mon50/tsumu-legal` の後継。Tsumu から Izure への改名に伴い公開先を移した。
旧 URL（`https://mon50.github.io/tsumu-legal/...`）は残していない。

## 公開 URL

ベース URL: `https://mon50.github.io/izure-legal/`

| ドキュメント | ja | en |
|---|---|---|
| プライバシーポリシー | `/legal/privacy/ja/` | `/legal/privacy/en/` |
| 利用規約 | `/legal/terms/ja/` | `/legal/terms/en/` |
| 特定商取引法に基づく表記 | `/legal/tokushoho/ja/` | `/legal/tokushoho/en/` |

アプリからは `src/features/settings/legal-urls.ts` の `LEGAL_URLS` がこれらを指す。
ai-backend が URL 先のページを取りに行くときの User-Agent にも、連絡先としてベース URL が入る
（`ai-backend/robots.ts` の `IZURE_USER_AGENT`）。

## 更新手順

1. 本体 `tsumu` の `docs/` を編集・レビューする（正本）。
2. `docs/index.html` と `docs/legal/` をこのリポジトリへ写し、コミットして push する。
3. 改訂の記録は各 HTML の改訂履歴に残す。運用ルールは本体の
   `aidlc-docs/operations/legal-revision-policy.md`。

## `.nojekyll`

GitHub Pages は既定で Jekyll のビルドを通す。`.nojekyll` を置くと素通しになり、
置いたファイルがそのまま配信される。ビルドの失敗も、`_` で始まる名前が無視されることも起きない。
本体の `docs/_config.yml` はこのリポジトリへは写さない（Jekyll を使わないため）。

> 連絡先メールアドレスは `support@nichijo-update.com`（全プロダクト共通）。
