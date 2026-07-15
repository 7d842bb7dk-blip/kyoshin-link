# CLAUDE.md — プロジェクト引き継ぎメモ

## これは何
株式会社京伸(大阪・精密板金)の Instagram 用リンクまとめページ(リットリンク代替)。
単一の `index.html` で完結する静的サイト。ビルド・依存なし。
公式サイト: https://www.f-kyo-shin.co.jp/

## 公開先(重要)
- GitHub Pages で公開済み。https://github.com/7d842bb7dk-blip/kyoshin-link
  branch: main / root。index.html と .nojekyll は必須
- このフォルダは origin に接続済み(2026-07-15 設定)。認証は Git Credential Manager。
  更新フロー: index.html を編集 → commit → push で本番反映(数分)
- 過去の実験ファイル(index_3.html / kyoshin-link-site.zip / netlify.toml)は整理済み。
  assets/ の写真19枚は TODO#2(画像ローカル化)の素材として残してある(どのHTMLからも未参照)
- 注意: ブラウザから手動アップロードしていた頃、新版が index_3.html という別名で入り、
  本番の index.html が旧版のまま数日間放置されていた事故がある。push 後は必ず反映を確認する

## ユーザーについて
- Git・ターミナル操作は不慣れ。専門用語を避け、コマンドは全部こちらで実行する前提で
- これまではブラウザで GitHub に手動アップロードしていた。push の代行を期待して
  Claude Code に移行した

## 現在のデザイン状態
- ダークテーマ(#0c0e11)、赤(#e60b10/#ff2630)・黒・白のコーポレートカラー
- ロゴ: SVG 再現(六角形=赤3枚+黒3枚の三角形、白stroke縁取り / Kyo=赤 shin=黒 白縁)
  白縁は暗背景で黒が沈まないための必須要素
- signature: レーザー火花の canvas アニメ(#fx、z-index:0、destination-out フェード)
  ※ ユーザー環境(PC/Edge)で「火花が見えない」報告があり z-index を -2→0 に修正した経緯あり。
  直近の本番反映後の見え方は未確認。もし見えない場合は CSS-only 火花(過去に表示実績あり)へ
  切替を検討
- prefers-reduced-motion は意図的に無視(ユーザー要望)
- 「数字で見る京伸」: 会社提供PDFを画像化し base64 で index.html に直接埋め込み済み
  (data:image/jpeg 約224KB)。元PDFの数値: 設立2008 / 平均39.2歳 / 取引241社(2025) /
  材料費¥236,419,297 / 設備91台 / 従業員69名(男60女9) / 同業種42・異業種18・新卒4・他5

## 構成(index.html)
ヒーロー(ロゴ+動画+ステッカー) / Culture(20代主力・役職者若い・仲良し) /
数字で見る京伸(PDF画像) / Links(公式HP・公式LINE lin.ee/5tJsTLC・動画) /
Works(スライドショー) / Business(横スワイプ) / Pick up(設備+K-MAXパワーアーム) /
Spec / SNS / 下部固定バー(電話 072-889-5788 / 公式LINE)
※ 見積もり関連は全削除済み。K-MAXはマシン製造のみ(加圧トレーニングルーム事業は終了、載せない)

## TODO(優先順)
1. 本番で火花が表示されるか確認。ダメなら CSS-only 方式へ
   ※ 2026-07-15 まで本番は旧版 index.html を配信していたため、これまでの「見えない」報告は
     旧版を見ていた可能性がある。新版反映後にあらためて確認すること
2. 画像・動画のローカル化(現在 f-kyo-shin.co.jp からのホットリンク。assets/ に取り込み相対参照へ)
3. OGP画像(og:image)の設定
