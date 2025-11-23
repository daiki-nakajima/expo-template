# CLAUDE.md

このファイルはClaude Code (claude.ai/code) がこのリポジトリで作業する際のガイダンスを提供します。

## プロジェクト概要

これは、Expo開発のための汎用テンプレートリポジトリです。今後、新しいExpoプロジェクトを始める際の基盤として使用されることを想定しています。

### テンプレートリポジトリの特徴

- コード品質管理（ESLint、TypeScript strict mode）が設定済み
- テスト環境のセットアップが完了済み（現在準備中）
- ベストプラクティスに基づいたプロジェクト構造
- 再利用可能なコンポーネントとユーティリティ
- CI/CDパイプラインの基本設定（準備予定）

### 技術スタック

- TypeScriptを使用したExpo React Nativeプロジェクト
- ファイルベースルーティング（Expo Router）
- React Native の新アーキテクチャを使用
- クロスプラットフォーム開発対応（iOS、Android、Web）

## 主要コマンド

### 開発

```bash
npx expo start              # 開発サーバーを起動（インタラクティブメニュー付き）
npx expo start --ios        # iOSシミュレーターで起動
npx expo start --android    # Androidエミュレーターで起動
npx expo start --web        # Webブラウザで起動
```

### コード品質

```bash
npm run lint                # ESLintを実行（Expoプリセット使用）
npm run lint:fix            # ESLintで自動修正
npm run format              # Prettierでコードフォーマット
npm run format:check        # フォーマットのチェック
```

### 品質チェック（Claude Codeが毎回実行）

**重要**: Claude Codeは以下の品質チェックを毎回実行します：

- `npm run lint` - ESLintによるコード品質チェック
- `npm run format:check` - Prettierによるフォーマットチェック
- コミット時は自動的にpre-commitフック（Husky + lint-staged）が実行され、ステージングされたファイルに対してESLintとPrettierが適用されます

### プロジェクト管理

```bash
npm run reset-project       # 現在のコードをapp-example/に移動し、新しいapp/を作成
```

## アーキテクチャ

### ファイルベースルーティング

ルートは `app/` ディレクトリのファイル構造によって定義されます：

- `app/_layout.tsx` - ルートレイアウトコンポーネント
- `app/index.tsx` - ホーム画面 (/)
- `app/[...missing].tsx` - 404ハンドラー

### プロジェクト構造

- `/app` - ファイルベースルーティングを使用したメインアプリケーションコード
- `/app-example` - タブ、モーダル、コンポーネントを含む参考実装
- `/assets` - 画像と静的アセット
- `/components` - 再利用可能なUIコンポーネント（作成時）
- `/constants` - テーマとアプリケーション定数（作成時）
- `/hooks` - カスタムReactフック（作成時）

### TypeScript設定

- Strictモードが有効
- パスエイリアス設定済み: `@/*` はプロジェクトルートにマップ
- 絶対インポートを使用: `import { Component } from '@/components/Component'`

### 主要技術

- **Expo SDK 54** - マネージドReact Nativeフレームワーク
- **React Native 0.81.5** - 新アーキテクチャ有効
- **React 19.1.0** - 実験的コンパイラ使用
- **Expo Router** - ナビゲーション用
- **TypeScript** - strictモード有効

### 開発における注意事項

- テストフレームワークは現在設定中
- マネージドExpoワークフローを使用（ネイティブiOS/Androidディレクトリなし）
- Webビルド用に静的Web出力が設定済み
- 新しいコンポーネント作成時は既存のコードパターンに従う
- 一貫したテーマのためにapp-exampleの`ThemedText`と`ThemedView`コンポーネントを使用

### 設定済みのツール

- **ESLint** - Expo公式設定を拡張したコード品質チェック
- **Prettier** - コードフォーマッター（ESLintと統合済み）
- **Husky + lint-staged** - プリコミットフックによる自動品質チェック
- **TypeScript** - strict mode有効

### 今後の追加予定

- Jest/React Native Testing Libraryによるテスト環境
- GitHub ActionsによるCI/CD設定
- Storybookによるコンポーネントカタログ
- 環境変数管理の標準化
