# Mooovin WhatsApp誘導 LP

WhatsApp経由で日本の賃貸物件探しをサポートする外国人向けLP（社内テスト用）。

## ファイル構成

```
mooovin-lp/
├── index.html        # メインHTML（CSS・JSすべてインライン）
├── robots.txt        # 検索エンジンクロール禁止
├── README.md         # このファイル
└── images/
    ├── mooovin-logo.png       # ヘッダー・フッターロゴ
    ├── hero-single.jpg        # FV背景（左：女性）
    ├── hero-couple.jpg        # FV背景（右：カップル）
    ├── problems-hero.jpg      # 「お部屋探しは大変…」セクション画像
    ├── reason-01.png          # 選ばれる5つの理由 #1（取扱90,000件）
    ├── reason-02.png          # 選ばれる5つの理由 #2（専門家提案）
    ├── reason-03.png          # 選ばれる5つの理由 #3（多言語対応）
    ├── reason-04.png          # 選ばれる5つの理由 #4（保証人不要）
    ├── reason-05.png          # 選ばれる5つの理由 #5（オンライン完結）
    └── support-services.png   # 【未配置】日本生活サポート画像
```

## デプロイ

GitHub Pages 等の静的ホスティングに `mooovin-lp/` 配下をそのまま配置すれば動作します。

## 検索インデックス除外

以下2層で対策済み：
- `<meta name="robots" content="noindex, nofollow, noarchive, nosnippet">`
- `robots.txt` で `Disallow: /`

本番公開時は両方とも解除してください。

## 要対応TODO

### 1. `images/support-services.png` の配置
日本の生活サポート画像（サポート項目が円形に配置されたデザイン画像）を `images/` フォルダに配置してください。配置されるまでサポートセクションは画像欠落表示になります。

### 2. WhatsApp URLの差し替え
`index.html` の以下5箇所＋JS変数を実際のMooovin WhatsAppビジネスURLに変更してください。

```js
var WHATSAPP_URL = 'https://wa.me/8100000000'; // ← この箇所
```

JS側で `data-whatsapp` 属性のあるリンクは全て自動で書き換わるので、ハードコードされた `wa.me/8100000000` を直接編集すればOKです。

### 3. 仮素材の差し替え（必要に応じて）
PIXTAの仮素材（hero画像など）は実際のMooovin撮影素材があれば差し替えてください。
