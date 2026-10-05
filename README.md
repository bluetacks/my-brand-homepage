# my-brand-homepage

スナックふるむーん公式HP初版。スマホ優先の1ページで、HTML/CSS/JavaScriptのみ。インストールやビルドは不要です。

## 公開（GitHub Pages）

1. このリポジトリの **Settings → Pages** を開く。
2. **Build and deployment → Source → Deploy from a branch** を選ぶ。
3. **Branch: main / Folder: /(root)** を選び **Save**。
4. Pagesに表示される公開完了を待ち、次のURLを開く。

https://bluetacks.github.io/my-brand-homepage/

GitHub公式手順: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## プレビュー

- リポジトリの **Code → Download ZIP** で保存・展開して `index.html` をブラウザで開く。そのまま写真・CSS・メニュー・FAQが動きます。
- スマホ表示はブラウザの開発者ツールのデバイス表示で確認。実機では公開後のURLを開く。
- ローカルサーバーが必要なら、このフォルダで `python -m http.server 4173 --bind 127.0.0.1` を実行し、`http://127.0.0.1:4173/` を開く。

## 構成

```text
index.html          本文・料金・SEO・OGP・JSON-LD
style.css           モバイル優先のレスポンシブデザイン
script.js           スマホメニュー（FAQはHTMLのdetails）
images/logo.webp    Driveの正式な透過ロゴをWebPへ変換
images/fullmoon_logo_transparent.png  Driveの元画像
images/ogp.jpg      SNS用1200×630画像
images/favicon.svg 月のファビコン
robots.txt
sitemap.xml
.nojekyll           Jekyll処理を使用しない
```

## 情報の根拠と未確認事項

- 料金は2026-10-05の依頼で指定された金額を掲載。外部掲載の異なる金額には置き換えていません。
- リニューアル日はユーザー確認により **2026-10-02**（当初の9/20から修正）。
- 住所・電話・月〜土20:00〜24:00／日19:00〜24:00・20代〜50代スタッフ・Instagramは、ユーザーが指定したGoogle店舗プロフィールを2026-10-05に確認。
  - https://share.google/1cCIywDGA9ouHFDWs
  - https://www.instagram.com/furumunsunakku/
- 最寄り駅から徒歩約8分、屋台村近くは店舗の外部紹介情報。https://www.snackyokocho.com/snack/19618/?from_area=2637
- ロゴはDrive「店舗画像関係／ロゴ」の `fullmoon_logo_transparent.png`（1254×1254、302,884 bytes）を使用。元PNGを同梱し、Web用には透過を保持してWebPへ変換。トリミング・色変更・描き直しはしていません。
- **未確認**: 税込／税別、サービス料、ボトル代、セットに含まれるドリンク、休業日、スタッフ個人の掲載内容、正確な入口の写真・目印。HPでは税サ込や営業時間延長、無料サービス等を断定せず、店舗への確認導線を掲載しています。
- スタッフの顔写真・架空の名前・架空の店内写真は掲載していません。入口案内は建物の1階と電話案内までです。写真や詳しい目印が分かればアクセス欄に追加してください。

## 更新する場所

- 料金: `index.html` の `#price`、TOPの料金、FAQ、meta descriptionを一緒に更新。
- 店舗情報: `#access` とJSON-LDを一緒に更新。
- Instagram: 全リンクとJSON-LDの `sameAs` を更新。
- 独自ドメイン移行: canonical、og:url、og:image、JSON-LD中のサイトURL、robots.txt、sitemap.xmlを同じURLへ変更。
- `sitemap.xml` の `lastmod` はページの実際の更新日に合わせる。

## robots.txtについて

GitHubのプロジェクトPagesではファイルは `/my-brand-homepage/robots.txt` に配置されます。検索エンジンが参照するrobots.txtは通常ホスト直下の `/robots.txt` です。このファイルだけでホスト全体のクロール設定は変更できません。サイトマップはSearch Consoleへ直接登録できます。独自ドメインをこのサイトのルートに割り当てた場合はルートのrobots.txtとして利用できます。

## SEO

title / meta description / canonical / OGP / Twitter Card / LocalBusiness JSON-LD / sitemapを実装。JSON-LDには未確認の評価・価格帯・座標を追加していません。構造化データやサイトマップの用意は検索掲載やリッチリザルトの表示を保証するものではありません。


## 2026-10-05 表示修正

- 画面内の店名はDriveの正式な透過ロゴで表示。円形の全体を表示し、CSSの切り抜き・マスク・合成は廃止。文章中の不要な店名の繰り返しを整理。検索用メタ情報・画像の代替テキスト・構造化データには文字の店名を保持。
- ページの背景をロゴ内部の濃紺（#010a29）に合わせています。元画像の透過をそのまま使用し、背景を隠すための加工はしていません。
- TOPのロゴ・キャッチコピーの直下へInstagram／Googleマップへのリンクを配置。スマホではロゴとリンクを先に表示。
- TOP直後に公式Instagramのプロフィール／投稿プレビューと、Googleマップの共有画面から取得した店舗の埋め込み地図を追加。
- 外部サービスの表示内容には、サービス側が表示する店名も含まれます。ログイン状態や閲覧環境により埋め込み表示が制限される場合に備え、直接開くリンクを常設。
