# 概要
通信プロトコルの1つで、"Secure Sockets Layer"の略称。

"公開鍵暗号方式"で"共通鍵"の受け渡しを行い、その後は受け渡した"共通鍵"を作って"共通鍵暗号方式"(秘密鍵暗号方式)でやり取りすることで、通信の安全性を高める仕組み。

"SSL 3.0"の後のバージョンアップで"TLS 1.0"(Transport Layer Security)になった。その時点でSSLの歴史は終了。

- https: SSLによって暗号化されたhttp通信。
- 常時SSL: ウェブサイト内のすべてのコンテンツをhttpsで通信すること。

# 流れ
```mermaid
sequenceDiagram

  participant cl as クライアント
  participant sv as サーバー
  participant ca as 認証局

  cl->>sv: アクセス
  sv->>cl: サーバー証明書を送信(公開鍵入っている)
  cl->>ca: この証明書本物？
  ca->>cl: 本物！
  note over cl: 証明書から公開鍵を取得
  note over cl: 共通鍵を生成
  note over cl: 共通鍵を公開鍵によって暗号化
  cl->>sv: 暗号化した共通鍵を送信
  note over sv: 秘密鍵によって復号