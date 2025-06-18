---
marp: true
theme: default
class: title
paginate: true
---

# サンプルプレゼンテーション

## Marp PDF 変換システムのデモ

作成日: 2025 年 6 月 18 日

---

## 📋 アジェンダ

1. **システム概要**
2. **主な機能**
3. **使用方法**
4. **テーマの種類**
5. **まとめ**

---

## 🔧 システム概要

### GitHub Actions + Marp で PDF 生成

- **入力**: Markdown ファイル (.md)
- **処理**: Marp CLI による変換
- **出力**: PDF ファイル
- **保存**: GitHub リポジトリに自動コミット

### 特徴

- 🎨 **カスタム CSS 対応**
- 🎯 **手動実行 & ファイル選択**
- 📁 **フォルダ管理**
- ⚡ **高速変換**

---

## ⭐ 主な機能

### ファイル選択機能

- GitHub Actions の手動実行
- セレクトボックスでファイル選択
- フォルダとテーマの選択

### 4 つのテーマ

- `default.css` - グラデーション背景
- `corporate.css` - ビジネス向け
- `minimal.css` - シンプル
- `dark.css` - ダークテーマ

---

## 🚀 使用方法

### Step 1: ファイル準備

1. `slides/` フォルダに Markdown ファイルを配置
2. 必要に応じてカスタム CSS を `css/` フォルダに追加

### Step 2: Actions 実行

1. GitHub の **Actions** タブを開く
2. **Marp Markdown to PDF Converter** を選択
3. **Run workflow** をクリック
4. パラメータを入力して実行

### Step 3: 結果確認

- `pdf/` フォルダに生成された PDF を確認
- Artifacts からもダウンロード可能

---

## 🎨 テーマ比較

| テーマ        | 用途         | 特徴                   |
| ------------- | ------------ | ---------------------- |
| **default**   | 一般プレゼン | グラデーション、モダン |
| **corporate** | ビジネス     | 清潔、読みやすい       |
| **minimal**   | 学術発表     | シンプル、Apple 風     |
| **dark**      | 技術発表     | ダークモード、ネオン   |

---

## 💡 Markdown 記法の例

### 基本記法

```markdown
# 見出し 1

## 見出し 2

### 見出し 3

**太字** _斜体_ `コード`

- リスト 1
- リスト 2
```

### 特殊クラス

```markdown
<!-- class: center -->

# 中央揃えスライド

<div class="highlight">ハイライト</div>
```

---

<!-- class: center -->

## ✅ まとめ

### 実現できること

- ✨ Markdown から高品質な PDF を生成
- 🎨 カスタムテーマでブランディング
- ⚙️ GitHub Actions で自動化
- 📁 複数ファイルの管理

### 今後の拡張可能性

- 🔄 バッチ処理機能
- 🎭 追加テーマの開発
- 🚀 自動デプロイ連携

---

<!-- class: center -->

# ありがとうございました！

## 🎉 Happy Presenting!

**GitHub Actions** で簡単 PDF 変換を体験してください
