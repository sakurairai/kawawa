# Kawawa

SNS(X)の文字を、かわいく丸く、ちょっとざんねんなキャワワにします。

X (旧Twitter) の表示フォントを、ローカルフォントだけで強制上書きするChrome拡張です。

- 英字は Comic Sans 系
- 日本語は丸ゴシック系 (Hiragino Maru Gothic / Meiryo / Yu Gothic / Noto Sans JP)
- 外部フォントは読み込まない (Google Fonts等を使わない)
- CSSのみで実装、JSによるDOM走査なし

## インストール (開発者モード)

1. Chromeで `chrome://extensions/` を開く
2. 右上の **Developer mode** をONにする
3. **Load unpacked** をクリックし、`extension/` ディレクトリを選択する
4. `https://x.com/` を開いて表示を確認する

## 配布用zipの作成

`extension/` の中身をzipルート直下に入れた状態でアーカイブします (Chrome Web Storeはmanifest.jsonがzipのトップにあることを要求します)。

```sh
cd extension && zip -r ../kawawa.zip . -x "**/.DS_Store"
```

## アンインストール

`chrome://extensions/` でKawawaを削除、または無効化すれば元に戻ります。

## 対象サイト

- `https://x.com/*`
- `https://twitter.com/*`

## ファイル構成

```
kawawa/
├─ extension/        # 配布対象 (このディレクトリの中身をzip)
│  ├─ manifest.json  # Chrome拡張マニフェスト (Manifest V3)
│  ├─ content.css    # Xに注入するスタイル
│  └─ icons/         # 拡張アイコン (16/48/128px)
├─ README.md         # このファイル
├─ PRIVACY.md        # プライバシーポリシー
└─ LICENSE           # MITライセンス
```

## プライバシー

本拡張機能は外部通信・データ収集を一切行いません。詳細は [PRIVACY.md](./PRIVACY.md) を参照してください。

## ライセンス

[MIT](./LICENSE)
