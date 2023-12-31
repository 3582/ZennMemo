---
title: "Security（セキュリティ）"
---
コンピューターセキュリティは、情報技術システムを不正アクセス、破壊、変更、盗難、または情報の漏洩から保護するための措置です。この分野は、多くの重要なトピックを含んでいます。主なトピックは以下の通りです。

#### OSIモデルとTCP/IPモデル

- OSIモデルとTCP/IPモデルは、ネットワーク通信の基本的な枠組みを提供し、セキュリティの観点からも重要です。

#### HTTPとDNS

- HTTP（Hypertext Transfer Protocol）とDNS（Domain Name System）は、ウェブ通信の基本的なプロトコルであり、セキュリティの観点から重要です。

#### TLSとHTTPS

- TLS（Transport Layer Security）とHTTPS（HTTP Secure）は、インターネット上での安全な通信を保証するためのプロトコルです。

#### 公開鍵暗号

- 公開鍵暗号は、データの暗号化とデジタル署名に使用される重要な技術です。

#### ハッシュ、暗号化、エンコーディング

- ハッシュ、暗号化、エンコーディングは、データの安全性を保つために使用される技術です。

#### OWASPトップ10

- OWASPトップ10は、ウェブアプリケーションのセキュリティに関する最も一般的な脆弱性をリストアップしたものです。

### Security（セキュリティ）に関する問題

#### 1. OSIモデルとTCP/IPモデルの違いは何ですか？

:::details 解答
OSIモデルは7層の理論的なモデルで、ネットワーク通信の各層を詳細に分けています。一方、TCP/IPモデルは4層の実用的なモデルで、インターネットの基礎となっています。
:::

#### 2. HTTPSとHTTPの違いは何ですか？

:::details 解答
HTTPSはHTTPにセキュリティ層（SSL/TLS）を追加したもので、暗号化された安全な通信を提供します。HTTPは暗号化されていないため、データが第三者によって読み取られる可能性があります。
:::

#### 3. 公開鍵暗号とは何ですか？その一般的な使用例を挙げてください。

:::details 解答
公開鍵暗号は、暗号化と復号に異なる鍵（公開鍵と秘密鍵）を使用する暗号方式です。一般的な使用例としては、デジタル署名やSSL/TLSによる通信の暗号化があります。

```bash
# OpenSSLを使用した公開鍵暗号の例
openssl genrsa -out private.pem 2048
openssl rsa -in private.pem -pubout -out public.pem
```

:::

#### 4. OWASPトップ10とは何ですか？その一例を挙げてください。

:::details 解答
OWASPトップ10は、ウェブアプリケーションのセキュリティに関する最も一般的な脆弱性をリストアップしたものです。一例としては、SQLインジェクションがあります。

```sql
# SQLインジェクションの例
SELECT * FROM users WHERE username = 'admin' --' AND password = 'password';
```

:::

#### 5. ハッシュ、暗号化、エンコーディングの違いは何ですか？

:::details 解答
ハッシュはデータを一方向の固定長の値に変換するプロセスです。暗号化はデータを秘密鍵を使って読めない形式に変換するプロセスです。エンコーディングはデータを特定の形式（例えばBase64）に変換するプロセスです。

```bash
# ハッシュの例（SHA-256）
echo -n "Hello World" | sha256sum

# 暗号化の例（AES）
openssl enc -aes-256-cbc -in secret.txt -out encrypted.txt

# エンコーディングの例（Base64）
echo -n "Hello World" | base64
```

:::
