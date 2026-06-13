# 京伸 リンクページ (kyoshin-link-site)

株式会社京伸の Instagram 用リンクまとめページ。
単一の `index.html` だけで動く静的サイト。ビルド不要。

## ローカルで確認する
このフォルダで以下のどちらかを実行し、ブラウザで http://localhost:8000 を開く。

```bash
# Python がある場合
python3 -m http.server 8000

# Node がある場合
npx serve .
```

## 公開する(おすすめ順)
1. **Netlify / Cloudflare Pages / GitHub Pages** にこのフォルダを上げる(無料・常時公開)
2. Git 管理 → ホスティング連携で自動デプロイ

## 構成
- `index.html` … ページ本体(HTML/CSS/JS すべて内包)
- `CLAUDE.md` … Claude Code 用のプロジェクト背景メモ
- `assets/` … (今は空)画像を取り込む場合の置き場所

詳しい背景・デザイン方針・TODO は `CLAUDE.md` を参照。
