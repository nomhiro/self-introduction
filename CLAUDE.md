# CLAUDE.md

野村宏樹の自己紹介ページ。GitHub Pages で https://nomhiro.github.io/self-introduction/ に公開。

## アーキテクチャ

- **`index.html` 1ファイル完結**（HTML + インライン CSS + インライン JS、約700行）。ビルド・依存・フレームワークなし。この構成を維持すること（CSS/JS を外部ファイルに分割しない）。
- 2ビュー構成: `<div class="view" data-view="biz">`（経営層向け）と `data-view="tech"`（技術者向け）。トップバーの `.seg-btn` で切替。
- 各ビューは A4 印刷用の `.sheet`（210mm × 297mm）の連なり。`@page { size: A4 }` + `.sheet.brk`（page-break-after）で印刷/PDF レイアウトを制御。

## デプロイとブランチ構成（重要）

- **GitHub Pages は `main` ブランチ（デフォルトブランチ）の root から配信**（legacy build）。`main` にマージされるまで公開されない。
- 過去に「Pages が更新されない」問題があり、原因対策としてキャッシュ抑止 meta タグ（Cache-Control / Pragma / Expires）を `<head>` に追加済み。**削除しないこと**。

## 編集時の注意

- **両ビューの整合性**: 連絡先・資格・実績など共通情報を変更するときは、biz / tech 両方のビューを確認して更新する。
- **印刷レイアウト**: フォントサイズ・余白は A4 に収まるよう mm / px 単位で細かく調整されている。コンテンツ追加後はブラウザの印刷プレビュー（A4・余白なし）で1ページに収まるか確認する。
- **印刷時の背景色**: `*` セレクタに `-webkit-print-color-adjust: exact; print-color-adjust: exact` を全体適用済み。削除すると印刷/PDFでバッジ等の色が消える。
- **レスポンシブCSSは `@media screen and (max-width:820px)` にすること**: `screen and` を外すと、A4の紙幅（210mm≒794px）が820px未満のため印刷時にモバイルレイアウトが適用され、PDFが崩れて3ページ化する（実際に起きた不具合）。
- **印刷検証**: `chrome --headless --no-pdf-header-footer --print-to-pdf=out.pdf http://localhost:8000/index.html` でPDF化し、2ページに収まるか・色が出ているかを確認できる。
- `.nojekyll` により Jekyll は無効（`_config.yml` は実質未使用）。アンダースコア始まりのファイルもそのまま配信される。
- コンテンツは日本語。トーンは「です・ます」調、本人一人称の実績紹介。

## 動作確認

```powershell
start index.html          # ブラウザで直接開く
python -m http.server 8000  # または簡易サーバー
```

ビュー切替ボタン・印刷ボタンの動作と、印刷プレビュー（Ctrl+P）での A4 レイアウトを確認する。
