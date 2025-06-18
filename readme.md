# 🎯 Marp PDF 変換システム

GitHub Actions と Marp を使用して Markdown ファイルをプロフェッショナルな PDF に変換するシステムです。

![Marp](https://img.shields.io/badge/Marp-Enabled-brightgreen)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-Automated-blue)
![License](https://img.shields.io/badge/License-MIT-yellow)

## ✨ 主な機能

- 🎨 **5 つのプロフェッショナルテーマ**
- 🚀 **GitHub Actions による自動変換**
- 📱 **手動実行 & ファイル選択**
- 🎯 **ローカル開発サポート**
- 📁 **整理されたフォルダ構成**
- ⚡ **高速 PDF 生成**

## 🎨 利用可能なテーマ

| テーマ        | 用途         | 特徴                       | プレビュー            |
| ------------- | ------------ | -------------------------- | --------------------- |
| **default**   | 一般プレゼン | グラデーション背景、モダン | 🌈 カラフル           |
| **corporate** | ビジネス基本 | 清潔、シンプル             | 🏢 プロフェッショナル |
| **compact**   | 文字多め     | 文字サイズ調整、省スペース | 📝 コンパクト         |
| **minimal**   | 学術発表     | Apple 風、ミニマル         | 🍎 シンプル           |
| **dark**      | 技術発表     | ダークモード、ネオン効果   | 🌙 ダーク             |

## 📁 プロジェクト構成

```
marp-wp-maker/
├── .github/workflows/
│   └── marp-pdf.yml           # GitHub Actions ワークフロー
├── css/
│   ├── default.css           # グラデーションテーマ
│   ├── corporate.css         # ビジネステーマ
│   ├── compact.css           # コンパクトテーマ
│   ├── minimal.css           # ミニマルテーマ
│   └── dark.css              # ダークテーマ
├── slides/
│   └── sample-presentation.md # サンプルプレゼンテーション
├── pdf/                      # 生成されたPDFファイル
├── .gitignore               # Git除外設定
└── README.md                # このファイル
```

## 🚀 クイックスタート

### 1. リポジトリのクローン

```bash
git clone https://github.com/your-username/marp-wp-maker.git
cd marp-wp-maker
```

### 2. GitHub Actions で実行

1. **GitHub** → **Actions タブ** → **Marp Markdown to PDF Converter**
2. **Run workflow** をクリック
3. パラメータを入力：
   - **MD ファイル名**: `sample-presentation.md`
   - **ソースフォルダ**: `slides`
   - **出力フォルダ**: `pdf`
   - **テーマ**: `compact.css`
4. **Run workflow** で実行

### 3. 結果確認

- `pdf/` フォルダに生成された PDF ファイル
- Actions の **Artifacts** からダウンロード

## 💻 ローカル開発

### 必要なツール

```bash
# Node.js のインストール確認
node --version
npm --version

# Marp CLI のインストール
npm install -g @marp-team/marp-cli

# インストール確認
marp --version
```

### 基本的な使用方法

```bash
# デフォルトテーマでPDF生成
marp slides/sample-presentation.md --pdf --output pdf/output.pdf

# カスタムテーマでPDF生成
marp slides/sample-presentation.md --pdf --theme css/compact.css --output pdf/output.pdf

# HTMLプレビュー生成
marp slides/sample-presentation.md --html --theme css/default.css --output preview.html

# ライブプレビュー（開発用）
marp slides/sample-presentation.md --server --theme css/corporate.css
```

### 全テーマ一括変換

```bash
# すべてのテーマでPDF生成
marp slides/sample-presentation.md --pdf --theme css/default.css --output pdf/sample-default.pdf
marp slides/sample-presentation.md --pdf --theme css/corporate.css --output pdf/sample-corporate.pdf
marp slides/sample-presentation.md --pdf --theme css/compact.css --output pdf/sample-compact.pdf
marp slides/sample-presentation.md --pdf --theme css/minimal.css --output pdf/sample-minimal.pdf
marp slides/sample-presentation.md --pdf --theme css/dark.css --output pdf/sample-dark.pdf
```

## 📝 Markdown ファイルの作成

### 基本構造

```markdown
---
marp: true
theme: default
class: title
paginate: true
---

# プレゼンテーションタイトル

## サブタイトル

作成日: 2025 年 6 月 18 日

---

## スライド内容

内容をここに記述します。

---

# 次のスライド

さらなる内容...
```

### 文字量調整のコツ

```markdown
<!-- 通常のスライド -->

## 普通の見出し

<!-- 文字が多い場合（compactテーマ使用時） -->
<!-- class: ultra-compact -->

## 詳細な内容のスライド
```

### 2 カラムレイアウト

```markdown
<div class="two-column">

<div>

## 左側の内容

- 項目 1
- 項目 2

</div>

<div>

## 右側の内容

- 項目 A
- 項目 B

</div>

</div>
```

## 🎨 テーマのカスタマイズ

### 新しいテーマの作成

1. `css/` フォルダに新しい CSS ファイルを作成
2. Marp のテーマ記法に従ってスタイルを定義
3. GitHub Actions の設定ファイルに追加

```css
/* 新しいテーマの例 */
@import "default";

section {
  background: #your-background-color;
  color: #your-text-color;
  font-family: "your-font";
}

h1 {
  color: #your-heading-color;
  font-size: 3em;
}
```

### GitHub Actions の設定更新

`.github/workflows/marp-pdf.yml` の `css_theme` オプションに追加：

```yaml
css_theme:
  type: choice
  options:
    - "default.css"
    - "corporate.css"
    - "compact.css"
    - "minimal.css"
    - "dark.css"
    - "your-custom.css" # 新しいテーマを追加
```

## 🔧 トラブルシューティング

### よくある問題

#### 1. 文字がページからはみ出る

**解決法**：

- `compact.css` テーマを使用
- Markdown で `<!-- class: ultra-compact -->` を追加
- 内容を複数スライドに分割

#### 2. CSS テーマが適用されない

**解決法**：

```bash
# ファイル存在確認
ls css/

# パス確認
marp slides/file.md --pdf --theme css/theme-name.css --output pdf/output.pdf
```

#### 3. GitHub Actions でエラー

**解決法**：

- ファイル名の確認（大文字小文字含む）
- フォルダパスの確認
- Actions のログを確認

#### 4. 日本語フォントの問題

**解決法**：
CSS でフォントを指定：

```css
section {
  font-family: "Noto Sans JP", "Hiragino Sans", sans-serif;
}
```

## 📚 参考資料

### Marp 関連

- [Marp 公式サイト](https://marp.app/)
- [Marp CLI](https://github.com/marp-team/marp-cli)
- [Marpit Markdown](https://marpit.marp.app/markdown)

### GitHub Actions

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [workflow_dispatch](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#workflow_dispatch)

## 🤝 コントリビューション

1. このリポジトリをフォーク
2. 機能ブランチを作成 (`git checkout -b feature/amazing-feature`)
3. 変更をコミット (`git commit -m 'Add amazing feature'`)
4. ブランチにプッシュ (`git push origin feature/amazing-feature`)
5. プルリクエストを作成

## 📄 ライセンス

MIT License - 詳細は [LICENSE](LICENSE) ファイルを参照してください。

## 🎉 サンプル出力

### デフォルトテーマ

- グラデーション背景
- モダンなデザイン
- 一般的なプレゼンテーションに最適

### コンパクトテーマ

- 文字が多いスライドに対応
- ビジネス文書向け
- 情報密度の高いプレゼンテーション

### ダークテーマ

- ダークモード対応
- 技術プレゼンテーションに最適
- ネオン効果で注目を集める

---

**Happy Presenting! 🚀**

質問やフィードバックがあれば、Issues で気軽にお知らせください。
