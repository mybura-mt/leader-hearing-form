# リーダー講座 事前ヒアリングシート

## セットアップ手順

### 1. Resend でAPIキーを取得（無料・月3000通）

1. https://resend.com にアクセス → 無料登録（メールアドレスで可）
2. ダッシュボード → 「API Keys」→「Create API Key」
3. 取得したキー（`re_xxx...`）をコピー

### 2. ローカルで動かす

```bash
cd ヒアリングフォーム
npm install
cp .env.example .env
# .env を開いて RESEND_API_KEY=re_xxx... に設定
node server.js
# → http://localhost:3000 で確認
```

### 3. Railway（無料）に公開する

1. https://railway.app に GitHub アカウントでログイン
2. 「New Project」→「Deploy from GitHub repo」→ このフォルダをプッシュしたリポジトリを選択
3. 環境変数を設定: `RESEND_API_KEY` = 取得したAPIキー
4. デプロイ完了 → 自動で公開URLが発行される

---

## 📧 メールアドレスの変更方法

`config.js` を開いて `TO_EMAIL` を変更するだけです：

```js
TO_EMAIL: '新しいメールアドレス@example.com',
```

変更後 `node server.js` を再起動（Railway の場合は再デプロイ）。

---

## ファイル構成

```
ヒアリングフォーム/
├── index.html   ← フォーム画面
├── server.js    ← メール送信バックエンド
├── config.js    ← 送信先メール等の設定（ここを変更）
├── package.json
└── .env.example ← APIキー設定テンプレート
```
