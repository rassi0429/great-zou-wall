# グレートエビチリウォール

Cloudflare Workersで動作するMisskey APIおよびActivityPub inboxへのNGワードフィルターです。

シュリンピア帝国内での利用を想定して開発していますが、Cloudflareに通したMisskeyという環境であれば、よそでもおそらく動くと思います。

## 利用方法

1. `npx wrangler kv:namespace create KV` でKVを作成する

2. 払い出された `id` で、 `wrangler.toml` の `kv_namespaces.id` を置き換える

3. `pnpm run deploy` でデプロイする

4. KVに「badWords」というキーでNGワードを登録する（ `;` で区切ると複数個登録できます）

5. Workers Routesにルートを追加する
  - `あなたのドメイン/api/notes/create`
  - `あなたのドメイン/api/i/update`
  - `あなたのドメイン/inbox`
  - `あなたのドメイン/users/*`

## ライセンス

CC0
