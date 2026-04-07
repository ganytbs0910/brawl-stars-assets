# brawl-stars-assets

ブロスタアプリ用のアセットCDNリポジトリ。jsDelivr経由で配信されます。

## CDN URL形式

```
https://cdn.jsdelivr.net/gh/ganytbs0910/brawl-stars-assets@main/MapImages/{filename}.png
https://cdn.jsdelivr.net/gh/ganytbs0910/brawl-stars-assets@main/manifest.json
```

## 構成

- `manifest.json` - マップ名(日本語) → ファイル名 のマッピング
- `MapImages/` - マップ画像PNG群

## 新マップを追加するには

1. `MapImages/` にPNGを追加（命名規則: `Snake_Case.png`）
2. `manifest.json` の `maps` に `"日本語名": "FileName.png"` を追加
3. commit & push
4. アプリは次回起動時に自動で取得（jsDelivr CDNが反映するまで5〜10分かかる場合あり）

## マニフェスト再生成

メインアプリ側で:
```
node scripts/generate-asset-manifest.mjs
```

これで `asset_repo/` の内容が更新されるので、ここからpushしてください。
