---
title: "プログラミング言語"
---

## 主要なプログラミング言語

| 言語       | パラダイム               | 主な用途                                    | 特徴                                               |
| ---------- | ------------------------ | ------------------------------------------- | -------------------------------------------------- |
| Python     | オブジェクト指向、命令型 | Web 開発、データ分析、AI、教育              | シンプル、動的型付け、リッチなライブラリ           |
| Java       | オブジェクト指向         | Web アプリ、Android アプリ、組み込み        | プラットフォーム独立、JVM 上で動作、WORA           |
| JavaScript | オブジェクト指向、関数型 | Web フロントエンド、サーバーサイド(Node.js) | Web ブラウザで動作、非同期処理が得意               |
| C          | プロシージャル           | システムプログラミング、組み込み、OS 開発   | 低レベルアクセス可能、高速                         |
| C++        | オブジェクト指向、命令型 | システム/アプリ開発、ゲーム開発             | C の上にオブジェクト指向等の機能追加、STL 利用可能 |
| C#         | オブジェクト指向         | Windows アプリ、Web アプリ、ゲーム開発      | .NET フレームワーク上で動作、Windows 向け          |
| Ruby       | オブジェクト指向         | Web 開発(Rails)、スクリプティング           | 人間中心の設計思想、動的型付け                     |
| Go         | 並行処理、命令型         | クラウド、マイクロサービス、並行処理タスク  | 静的型付け、組み込みのゴルーチンでの並行処理       |
| Swift      | オブジェクト指向         | iOS/macOS アプリ開発                        | Apple 製品向け、型安全、モダンな構文               |

### 1. Python

- **特徴**: インタープリタ型、動的型付け、汎用性の高い言語。
- **用途**: Web 開発、データ解析、人工知能、教育、スクリプティングなど多岐にわたる。

### 2. Java

- **特徴**: オブジェクト指向、プラットフォーム独立、WORA (Write Once, Run Anywhere) の哲学。
- **用途**: Web アプリケーション、Android アプリ開発、組み込みシステム。

### 3. JavaScript (JS)

- **特徴**: Web ブラウザ内で動作するスクリプト言語、非同期処理が得意。
- **用途**: Web ページのインタラクティブ性向上、Node.js を使用したサーバーサイド開発。

### 4. C

- **特徴**: プロシージャル、低レベルアクセス可能、高速。
- **用途**: システムプログラミング、組み込みシステム、OS の開発。

### 5. C++

- **特徴**: C 言語にオブジェクト指向やテンプレートなどの機能を追加した言語。
- **用途**: システム/アプリケーションソフトウェアの開発、ゲーム開発、高性能アプリケーション。

### 6. C#

- **特徴**: Microsoft が開発し、.NET フレームワーク上で動作する。
- **用途**: Windows アプリケーション、Web アプリケーション、Unity ゲームエンジンでのゲーム開発。

### 7. Ruby

- **特徴**: 簡潔で人間中心の設計思想、動的型付け。
- **用途**: Web 開発 (特に Ruby on Rails フレームワーク)、スクリプティング。

### 8. Go (Golang)

- **特徴**: Google が開発した静的型付け、並行処理機能が組み込まれた言語。
- **用途**: クラウドシステム、マイクロサービス、並行処理タスク。

### 9. Swift

- **特徴**: Apple が開発し、型安全と高速性を追求した言語。
- **用途**: iOS, macOS, watchOS, tvOS のアプリ開発。

## Python

### Q1: Pythonのリストとタプルの主な違いは何ですか？
:::details Click for Answer

  リストは可変（変更可能）、タプルは不変（変更不可）。リストは`[]`で定義され、タプルは`()`で定義される。

:::

### Q2: `lambda` 関数の特徴や利点を述べてください。
:::details Click for Answer

  `lambda`は匿名関数を作成するためのツール。簡潔に一時的な関数を定義できる。

:::

---

## Java

### Q3: Javaのガベージコレクションの役割は何ですか？
:::details Click for Answer

  不要になったメモリ（オブジェクト）を自動的に解放する役割。メモリリークを防ぎ、メモリの効率的な使用を支援する。

:::

### Q4: Javaでのオーバーロードとオーバーライドの違いを説明してください。
:::details Click for Answer

  オーバーロードは同じ名前のメソッドを異なるパラメータで複数定義すること。オーバーライドはサブクラスでスーパークラスのメソッドを再定義すること。

:::

---

## JavaScript (JS)

### Q5: `let`, `const`, `var` の違いについて説明してください。
:::details Click for Answer

  `var`は関数スコープ、`let`と`const`はブロックスコープ。`const`は再代入不可。

:::

### Q6: JavaScriptでのプロミス (Promise) の役割は何ですか？
:::details Click for Answer

  非同期操作の結果を表現するオブジェクト。成功（resolve）または失敗（reject）の状態を持つ。

:::

---

## C

### Q7: ポインタとは何でしょうか？
:::details Click for Answer

  メモリ上のアドレスを保存・参照するための変数。

:::

### Q8: `static` キーワードがC言語で果たす役割を説明してください。
:::details Click for Answer

  関数や変数の可視性をファイル内に制限したり、変数の生存期間をプログラムの実行時間全体に拡張する。

:::

---

## C++

### Q9: C++におけるRAIIとは何ですか？
:::details Click for Answer

  Resource Acquisition Is Initialization。リソースを取得する際にオブジェクトを初期化し、オブジェクトのデストラクタでリソースを解放する。

:::

### Q10: C++のSTLにはどのようなコンテナが存在しますか？
:::details Click for Answer

  ベクター（vector）、リスト（list）、セット（set）、マップ（map）など。

:::

---

## C#

### Q11: C#でのイベントとデリゲートの関係を説明してください。
:::details Click for Answer

  デリゲートは関数への参照を保持するオブジェクト。イベントはデリゲートの特殊なインスタンスで、外部から直接呼び出しを制限する。

:::

### Q12: `LINQ` の目的や利点は何ですか？
:::details Click for Answer

  Language Integrated Query。コレクションやデータベースを簡潔かつ統一的にクエリするための言語統合機能。

:::

---

## Ruby

### Q13: Rubyにおけるブロック、プロック、ラムダの違いは何ですか？
:::details Click for Answer

  ブロックはコードの塊、プロックはブロックをオブジェクト化したもの、ラムダはプロックの特殊な形であり、引数の数が厳格。

:::

### Q14: `@` や `@@` の接頭辞が変数にどのような意味を持たせるか説明してください。
:::details Click for Answer

  `@`はインスタンス変数、`@@`はクラス変数を示す。

:::

---

## Go (Golang)

### Q15: Go言語のゴルーチンの役割は何ですか？
:::details Click for Answer

  軽量スレッドのようなもので、効率的な並行処理を実現する。

:::

### Q16: Goのインターフェイスを利用するメリットを説明してください。
:::details Click for Answer

  型の実装を明示的に指定せずに、型の振る舞いを定義することができる。多態性を実現する。

:::

---

## Swift

### Q17: Swiftにおけるオプショナル型の目的とは何ですか？
:::details Click for Answer

  値が存在するか、存在しない（nil）かの状態を安全に表現する。

:::

### Q18: Swiftの`struct`と`class`の違いを説明してください。
:::details Click for Answer

  `struct`は値型、`class`は参照型。`struct`はコピーされるが、`class`は参照が渡される。

:::

