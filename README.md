# self-introduction

野村 宏樹（しろくま / [@nomhiro](https://github.com/nomhiro)）の自己紹介ページ。

## 👉 公開ページ

**https://nomhiro.github.io/self-introduction/**

## 概要

GitHub Pages で公開している単一 HTML の自己紹介ページです。ビルド不要・依存なしで、`index.html` 1ファイルにスタイルとスクリプトをすべて含みます。

- **2つの表示切替**: 「経営層向け」と「技術者向け」をトップバーのボタンで切替
- **印刷 / PDF 対応**: A4 サイズ（210mm × 297mm）でそのまま印刷・PDF 化できるレイアウト
- **日本語デザイン**: しっぽり明朝 + Zen角ゴシック + IBM Plex Mono（Google Fonts）

## ファイル構成

```
index.html   # ページ本体（HTML + インライン CSS + インライン JS）
photo.jpg    # プロフィール写真
.nojekyll    # GitHub Pages の Jekyll 処理を無効化
_config.yml  # theme: null（.nojekyll があるため実質未使用）
```

## ローカルプレビュー

ビルド不要です。ブラウザで直接開くか、簡易サーバーを立てます。

```powershell
# ブラウザで直接開く
start index.html

# または簡易サーバー
python -m http.server 8000
# → http://localhost:8000
```

印刷レイアウトは、ブラウザの印刷プレビュー（Ctrl+P）で A4・余白なしで確認してください。

## デプロイ

`main` ブランチの root がそのまま GitHub Pages にデプロイされます（legacy build）。**`main` にマージされた時点で公開**されるため、変更は PR を `main` 宛てに作成してマージしてください。

反映が遅い場合はブラウザキャッシュの可能性があります（`index.html` にはキャッシュ抑止の meta タグを設定済み）。ハードリロード（Ctrl+Shift+R）を試してください。

## リンク

- GitHub: [github.com/nomhiro](https://github.com/nomhiro)
- Blog: [zenn.dev/nomhiro](https://zenn.dev/nomhiro)
- Microsoft MVP: [MVP プロフィール](https://mvp.microsoft.com/ja-JP/MVP/profile/93ebd9f1-a8c0-492c-8cc2-adc7f5f980e9)
