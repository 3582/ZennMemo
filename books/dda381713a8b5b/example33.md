---
title: "Server Sent Events"
---
- **Server Sent Events (SSE)**は、サーバーからクライアントへの一方向の通信を可能にする技術です。
- これにより、サーバーは新しい情報があるときにクライアントにデータをプッシュすることができます。
- SSEは特に、リアルタイムの更新が必要なウェブアプリケーションに適しています。

### Server Sent Eventsの特徴

- **一方向通信**: SSEはサーバーからクライアントへのみデータを送信します。
- **簡単な実装**: HTTPプロトコルを使用し、特別なプロトコルやソケット接続は不要です。
- **自動再接続**: 接続が切断された場合、クライアントは自動的に再接続を試みます。

### Server Sent Eventsの利点

- **リアルタイム更新**: ニュースフィード、株価の更新、ライブブログなど、リアルタイムでの情報更新が求められる場合に有効です。
- **軽量な通信**: WebSocketsに比べて軽量で、サーバーのリソースを節約できます。
- **広範なブラウザサポート**: 多くのモダンブラウザでサポートされています。

Server Sent Eventsは、サーバーからクライアントへの効率的な一方向通信を実現する技術です。リアルタイムのデータ更新が必要なウェブアプリケーションにおいて、簡単かつ効率的な解決策を提供します。

### 問題1: Server Sent Events (SSE)の主な用途は何ですか？

:::details 解答
Server Sent Eventsは、サーバーからクライアントへの一方向のデータストリームを提供するために使用されます。これは、リアルタイムの更新が必要なアプリケーション、例えばニュースフィード、株価のリアルタイム更新、ライブブログなどに適しています。
:::

### 問題2: Server Sent EventsとWebSocketsの主な違いは何ですか？

:::details 解答
Server Sent Eventsは一方向通信（サーバーからクライアントへ）に特化しているのに対し、WebSocketsは双方向通信をサポートします。SSEはHTTPプロトコル上で動作し、特別なプロトコルやソケット接続は必要ありませんが、WebSocketsは独自のプロトコル（ws://またはwss://）を使用します。
:::

### 問題3: JavaScriptでServer Sent Eventsを使用する基本的なコード例を示してください。

:::details 解答
JavaScriptでServer Sent Eventsを使用する基本的なコード例は以下の通りです：

```javascript
const eventSource = new EventSource('http://example.com/sse');

eventSource.onmessage = function(event) {
  console.log('New message:', event.data);
};

eventSource.onerror = function(event) {
  console.error('EventSource failed:', event);
};

// イベントソースを閉じる場合
// eventSource.close();
```

このコードは、指定されたURLからSSEを受信し、新しいメッセージがあるたびにそれをコンソールに表示し、エラーが発生した場合にはエラーをコンソールに表示します。
:::
