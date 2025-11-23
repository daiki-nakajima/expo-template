# Expo開発テンプレートリポジトリ

## 概要

このリポジトリは、Expo React Native開発のための汎用テンプレートです。新しいプロジェクトを素早く立ち上げるための基盤として設計されており、ベストプラクティスと品質管理ツールが事前設定されています。

## テンプレートの特徴

### ✅ 設定済みの機能

- **TypeScript** - 厳格な型チェック（strict mode）による安全なコード記述
- **ESLint** - Expoプリセットを使用したコード品質管理
- **Expo Router** - ファイルベースのルーティングシステム
- **React Native新アーキテクチャ** - 最新のパフォーマンス最適化
- **クロスプラットフォーム対応** - iOS、Android、Web対応
- **絶対パスインポート** - `@/`エイリアスによるクリーンなインポート

### 🚧 準備中の機能

- **テストフレームワーク** - Jest + React Native Testing Library
- **CI/CDパイプライン** - GitHub Actions統合
- **プリコミットフック** - Husky + lint-staged
- **コンポーネントカタログ** - Storybook統合
- **環境変数管理** - 開発/本番環境の分離

## プロジェクト構造

```
expo-template/
├── app/                    # メインアプリケーションコード
│   ├── _layout.tsx        # ルートレイアウト
│   ├── index.tsx          # ホーム画面
│   └── [...missing].tsx   # 404ハンドラー
├── app-example/           # 参考実装（タブ、モーダル等）
├── assets/                # 画像・静的アセット
├── components/            # 再利用可能なUIコンポーネント
├── constants/             # テーマ・アプリケーション定数
├── hooks/                 # カスタムReactフック
└── scripts/               # ユーティリティスクリプト
```

## 使用方法

### 1. テンプレートからプロジェクトを作成

```bash
# GitHubテンプレート機能を使用して新しいリポジトリを作成
# または、このリポジトリをクローン
git clone https://github.com/[your-username]/expo-template.git [your-project-name]
cd [your-project-name]
```

### 2. 依存関係のインストール

```bash
npm install
```

### 3. 開発サーバーの起動

```bash
# インタラクティブメニュー付きで起動
npx expo start

# プラットフォーム別に起動
npx expo start --ios        # iOSシミュレーター
npx expo start --android    # Androidエミュレーター
npx expo start --web        # Webブラウザ
```

### 4. プロジェクトのリセット（オプション）

既存の`app/`ディレクトリをクリーンな状態にしたい場合：

```bash
npm run reset-project
```

このコマンドは現在のコードを`app-example/`に移動し、新しい`app/`ディレクトリを作成します。

## 開発ガイドライン

### コード品質の維持

```bash
# Lintチェック
npm run lint
```

### コンポーネント作成時の注意

- 既存のコードパターンに従う
- `ThemedText`と`ThemedView`を使用して一貫したテーマを維持
- TypeScriptの型定義を必ず追加
- 絶対パスインポート（`@/`）を使用

### 推奨される開発フロー

1. 新機能はフィーチャーブランチで開発
2. コミット前にLintチェックを実行
3. 意味のあるコミットメッセージを記述
4. プルリクエストでコードレビューを実施

## 技術仕様

- **Expo SDK**: 54
- **React Native**: 0.81.5（新アーキテクチャ対応）
- **React**: 19.1.0（実験的コンパイラ使用）
- **TypeScript**: Strictモード有効
- **Node.js**: 18.x以上推奨

## 貢献方法

このテンプレートの改善に貢献していただける方は：

1. このリポジトリをフォーク
2. フィーチャーブランチを作成（`git checkout -b feature/amazing-feature`）
3. 変更をコミット（`git commit -m '新機能: 素晴らしい機能を追加'`）
4. ブランチにプッシュ（`git push origin feature/amazing-feature`）
5. プルリクエストを作成

## ライセンス

このプロジェクトはMITライセンスの下で公開されています。

## サポート

問題が発生した場合や質問がある場合は、[Issues](https://github.com/[your-username]/expo-template/issues)でお知らせください。

---

このテンプレートがあなたのExpo開発をより効率的にすることを願っています！ 🚀
