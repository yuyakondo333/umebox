This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.







--- 

了解です！README用に整理してMarkdown化しました👇

# Xクローン (Twitter Clone) 要件

## 概要
Twitterのクローンを作りますが、本家をそっくりそのまま再現するのは難しいため、以下の仕様とします。  
仕様に迷った場合は**最新のTwitterの仕様**に従うものとします。

---

## 基本機能

- ユーザー新規登録
- ユーザーログイン
- プロフィール登録・更新
  - ヘッダー画像
  - プロフィール画像
  - 名前
  - 自己紹介
  - 場所
  - ウェブサイト
  - 生年月日
- ツイート投稿（画像付き可）
- ツイート削除（編集は不可）
- コメント投稿・削除（編集は不可）
- リツイート
- いいね
- フォロー・フォロー解除
- 通知
  - 自分の投稿にいいねされたとき
  - フォローされたとき
  - ツイートにコメントがあったとき
- ダイレクトメッセージ（グループ対応）
- ツイートのブックマーク
- 退会

---

## 画面仕様
- 画面レイアウトはTwitterに準拠
  - ログイン後の画面は、左にサイドバー、中央にツイート一覧を表示
- そっくり作る必要はなく、大枠のレイアウトを踏襲する

---

## CSSフレームワーク
- 制限なし
- 推奨: Bootstrap など

---

## タスク一覧

### 新規登録機能
- **Golang**: 新規登録API
- **React**: 新規登録画面

### ログイン機能
- **Golang**: ログインAPI
- **React**: ログイン画面  
  - ログイン後はツイート一覧画面へ遷移（当初はプレースホルダー画面）

### ツイート投稿機能
- **Golang**: ツイート投稿API、画像アップロードAPI
- **React**: ツイート投稿フォーム（画像対応）

### ツイート一覧機能
- **Golang**: ツイート一覧API（全ユーザー、ページネーション `limit, offset`）
- **React**: ツイート一覧表示

### ツイート詳細
- **Golang**: ツイート詳細API
- **React**: ツイート詳細画面

### プロフィール画面
- **Golang**: プロフィール更新API、ユーザーごとのツイート一覧API  
  - `tweets` キーにツイート配列を返す
- **React**: プロフィール画面、プロフィール更新モーダル画面

### ツイート削除
- **Golang**: ツイート削除API
- **React**: プロフィール画面から削除可能

### コメント機能
- **Golang**: コメント投稿API、コメント一覧API、コメント削除API
- **React**: コメント投稿モーダル、コメント一覧画面（削除可）

### リツイート
- **Golang**: リツイートAPI、リツイート数を返す
- **React**: リツイートボタン、リツイート数表示

### いいね
- **Golang**: いいねAPI、いいね数を返す
- **React**: いいねボタン、いいね数表示

### フォロー・フォロー解除
- **Golang**: フォローAPI、アンフォローAPI
- **React**:  
  - ツイート一覧からプロフィールへ遷移  
  - プロフィール画面でフォロー・フォロー解除  
  - ボタン表示を動的に変更

### 通知
- **Golang**: 通知テーブルへの書き込み、通知一覧API
- **React**: 通知一覧画面

### ダイレクトメッセージ
- **Golang**:
  - グループ作成API
  - メッセージ投稿API
  - メッセージ一覧API
  - グループ一覧API
- **React**:
  - サイドバーからメッセージ画面へ遷移
  - グループ一覧画面
  - グループ詳細画面（メッセージ表示・投稿）

### ブックマーク
- **Golang**: ブックマークAPI、ブックマーク一覧API
- **React**: ブックマーク登録、ブックマーク一覧画面

### 退会
- **Golang**: 退会API
- **React**: サイドバーに退会ボタンを設置

---

このままREADMEに貼れば見やすくなります。
要件とタスクをさらに整理して「MVP（必須機能）」「追加機能」に分けることもできますが、やりますか？






