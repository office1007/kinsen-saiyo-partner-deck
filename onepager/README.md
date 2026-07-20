# 採用パートナー ペライチ（A4パンフレット）

企業配布用のA4 1枚パンフレット。`index.html` が唯一の実体です。

- 本番URL: https://saiyo-partner-onepager.vercel.app
- Vercelプロジェクト: `saiyo-partner-onepager`

## 更新手順

```sh
# 1. 編集
vi onepager/index.html

# 2. GitHubへ反映
git add onepager/index.html
git commit -m "ペライチ更新: <変更内容>"
git push origin main

# 3. 本番反映
cd onepager
vercel --prod --yes --scope office1007s-projects
```

## PDFで配る場合

本番URLをブラウザで開き、印刷 → PDFとして保存。
用紙A4・余白なしでA4 1枚に収まります。

## レイアウトの制約

`.sheet` を `210mm × 297mm` に固定しているため、**文章を足すとA4からはみ出します**。
追記する場合は、はみ出していないか確認してください。

```sh
# ページ数チェック（1 になればOK）
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless --disable-gpu --print-to-pdf=/tmp/check.pdf \
  --print-to-pdf-no-header "file://$PWD/index.html"
python3 -c "import re;print(len(re.findall(rb'/Type\s*/Page[^s]',open('/tmp/check.pdf','rb').read())))"
```

## 注意

以下は移行前の古いコピーです。編集しても本番には反映されません。

- `~/採用パートナー_ペライチ.html`
- `~/saiyo-partner-onepager/`
