# 情報科 授業計画

高校情報科（情報Ⅰ・情報Ⅱ）の授業計画を年度単位で管理するリポジトリです。

## サイト

GitHub Pages でドキュメントを公開しています。

## ディレクトリ構成

```
edu/
├── docs/
│   ├── _template/          # 各ファイルのテンプレート
│   ├── 2026/
│   │   ├── informa1/       # 情報Ⅰ（年間計画・単元計画・授業）
│   │   └── informa2/       # 情報Ⅱ（年間計画・単元計画・授業）
│   └── pbp/                # プロジェクトベース計画（PBP）
├── mkdocs.yml              # MkDocs 設定
└── .github/workflows/      # GitHub Actions（自動デプロイ）
```

## 使い方

### ローカルでプレビュー

```bash
pip install mkdocs-material
mkdocs serve
```

ブラウザで `http://localhost:8000` を開く。

### ファイルを追加・編集してプッシュ

```bash
git add .
git commit -m "コミットメッセージ"
git push origin main
```

プッシュ後、GitHub Actions が自動でビルド・デプロイします。

## スキル（Claude Code）

| スキル | 説明 |
|---|---|
| `/subject` | 科目ディレクトリと年間計画・評価・振り返りファイルを作成 |
| `/unit` | 単元ディレクトリと単元計画・授業ファイルを作成 |
