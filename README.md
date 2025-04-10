# Auth0 × Cloudflare Pages OIDC ログインデモ

このリポジトリは、**Cloudflare Pages** 上にデプロイできる、**Auth0によるログイン機能付きのシンプルなWebサイトのデモ**です。  
以下の2つのページで構成されています：

- `index.html`：公開用のランディングページ（ログインボタンあり）
- `protected.html`：ログイン後にのみアクセスできるページ

---

## 🚀 主な機能

- **Cloudflare Pages** でホスティング
- **Auth0 Universal Login** による認証
- **OpenID Connect (OIDC)** によるIDプロバイダ（Entra ID、Googleなど）対応
- `protected.html` へのアクセス制御（クライアントサイド）

---

## `auth0.js` の設定を編集

`index.html` および `protected.html` のスクリプト中にある以下の部分を修正：

```js
const auth0Client = await createAuth0Client({
domain: "YOUR_AUTH0_DOMAIN",
client_id: "YOUR_CLIENT_ID",
redirect_uri: window.location.origin + "/protected.html"
});
```
※ YOUR_AUTH0_DOMAIN と YOUR_CLIENT_ID をAuth0管理画面から取得した値に置き換えてください。   

---   

## Cloudflare Pages にデプロイ

- GitHubリポジトリを Cloudflare Pages に接続
- ルートディレクトリは /
- ビルドステップは不要（静的ホスティング）
- [Deploy] を押して公開！



