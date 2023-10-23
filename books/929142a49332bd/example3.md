---
title: "データ構造"
---
このセクションでは、コンピュータサイエンスの基本となるデータ構造について学びます。以下に主要なトピックを示します。

- **Array（配列）**
- **Linked List（連結リスト）**
- **Stack（スタック）**
- **Queue（キュー）**
- **Hash Table（ハッシュテーブル）**
- **Graph（グラフ）**
- **Tree（ツリー）**
  - Heap（ヒープ）
  - Binary Tree（バイナリツリー）
  - Spanning Tree（スパニングツリー）
  - Binary Search Tree（バイナリサーチツリー）
  - Full Binary Tree（フルバイナリツリー）
  - Complete Binary Tree（コンプリートバイナリツリー）
  - Balanced Tree（バランスツリー）
  - Unbalanced Tree（アンバランスツリー）
- **Directed Graph（有向グラフ）**
- **Undirected Graph（無向グラフ）**

1. 配列(Array)とは何か説明してください。
   :::details 解答
   配列は、同じデータ型の要素がメモリ上に連続的に格納されるデータ構造です。各要素はインデックスまたはキーによって識別されます。以下はJavaのコード例です。

   ```java
   int[] myArray = new int[5]; // サイズ5の整数配列
   myArray[0] = 25; // インデックス0に25を設定
   ```

   :::

2. 連結リスト(Linked List)の特徴を2つ以上挙げてください。
   :::details 解答
   連結リストは、要素（ノード）がポインタで連結されているデータ構造で、ノード間の挿入や削除が容易であり、固定サイズでなく動的にサイズが変更可能です。以下はJavaのコード例です。

   ```java
   LinkedList<String> myLinkedList = new LinkedList<>();
   myLinkedList.add("Element1"); // 要素を追加
   myLinkedList.removeFirst(); // 最初の要素を削除
   ```

   :::

3. スタック(Stack)とキュー(Queue)の主な違いは何ですか？
   :::details 解答
   スタックは後入れ先出し（LIFO）原則に基づいており、最後に追加された要素が最初に取り出されます。キューは先入れ先出し（FIFO）原則に基づいており、最初に追加された要素が最初に取り出されます。以下はJavaのコード例です。

   ```java
   Stack<Integer> myStack = new Stack<>();
   myStack.push(5); // 要素を追加
   int topElement = myStack.pop(); // 最後に追加された要素を取り出す

   Queue<Integer> myQueue = new LinkedList<>();
   myQueue.add(7); // 要素を追加
   int firstElement = myQueue.poll(); // 最初に追加された要素を取り出す
   ```

   :::

4. ハッシュテーブル(Hash Table)が高速な検索操作を提供する理由を説明してください。
   :::details 解答
   ハッシュテーブルは、キーを特定のハッシュにマッピングすることで、要素への高速なアクセスを提供します。これにより、平均的な検索、挿入、削除の時間計算量が一定時間（O(1)）になります。以下はJavaのコード例です。

   ```java
   HashMap<String, String> myHashMap = new HashMap<>();
   myHashMap.put("Key1", "Value1"); // 要素を追加
   String value = myHashMap.get("Key1"); // キーによる要素の検索
   ```

   :::

5. バイナリツリーとバイナリサーチツリーの違いは何ですか？
   :::details 解答
   バイナリツリーは、各ノードが最大2つの子ノードを持つ階層的なデータ構造です。バイナリサーチツリー（BST）は、バイナリツリーの一種で、左の子ノードの値が親ノードの値より小さく、右の子ノードの値が親ノードの値より大きいという特性があります。以下はJavaのコード例です（簡略化されたバイナリサーチツリーの実装）。

   ```java
   class TreeNode {
     int value;
     TreeNode left;
     TreeNode right;

     TreeNode(int value) {
       this.value = value;
       left = null;
       right = null;
     }
   }

   public class BinaryTree {
     TreeNode root;

     // メソッドの追加 (挿入、検索など)
   }
   ```

   :::

6. バランスツリーとアンバランスツリーの違いを説明してください。
   :::details 解答
   バランスツリーは、左右のサブツリーの高さが均等またはほぼ均等で、検索、挿入、削除操作の最適化がされています。アンバランスツリーは、一方のサブツリーが他方よりも明らかに深い場合があり、これにより操作の効率が低下する可能性があります。バランスツリーの例としては、AVLツリーやRed-Blackツリーがありますが、これらの具体的な実装は複雑で、ここでは簡略化された例を示します。

    ```mermaid
    graph TB
        subgraph AVL Tree Operation
            Insert(Insert Node)
            CheckHeight{Check Height Difference}
            Rebalance(Rebalance Tree)
            Rotate{Rotate Nodes if necessary}
            Adjust(Adjust Tree Properties)
        end
        Insert --> CheckHeight
        CheckHeight -- Yes --> Rebalance
        CheckHeight -- No --> Adjust
        Rebalance --> Rotate
        Rotate --> Adjust
    ```

   ```java
   class AVLTreeNode {
       int value;
       int height; // ノードの高さ
       AVLTreeNode left;
       AVLTreeNode right;

       AVLTreeNode(int value) {
           this.value = value;
           this.height = 1; // 新しいノードは高さ1で初期化
           left = null;
           right = null;
       }
   }

   public class AVLTree {
       private AVLTreeNode root;

       // ノードの高さを取得
       private int height(AVLTreeNode N) {
           if (N == null)
               return 0;
           return N.height;
       }

       // ノードのバランスファクターを取得
       private int getBalance(AVLTreeNode N) {
           if (N == null)
               return 0;
           return height(N.left) - height(N.right);
       }

       // ツリーの回転やバランス調整などのメソッドをここに実装
       // ...
   }

   :::

7. 有向グラフと無向グラフにはどのような違いがありますか？
   :::details 解答
   有向グラフと無向グラフの主な違いは、エッジの方向性にあります。有向グラフでは、エッジには明確な方向があり、ノードからノードへの一方通行のパスを表します。これに対して、無向グラフでは、エッジに方向性がなく、ノード間の移動が双方向に自由です。

   例として、ソーシャルメディアのネットワークを考えることができます。無向グラフは、Facebookのように、フレンドシップが相互の関係である場合に使用されます。一方、有向グラフはTwitterのようなプラットフォームで使用され、フォローは一方向の関係を示します。
   このコード例では、グラフのノードとエッジを表す基本的な構造を設定し、有向グラフと無向グラフの間の関係の違いを示しています。具体的には、無向グラフでは双方向のエッジが形成され、有向グラフでは一方向のエッジが形成される点が異なります。

    ```mermaid
    graph TB
        %% 無向グラフの例
        subgraph 一部の無向グラフ
            A --- B
            B --- C
            C --- D
            D --- A
        end

        %% 有向グラフの例
        subgraph 一部の有向グラフ
            E --> F
            F --> G
            G --> H
            H --> E
        end
    ```

   以下は、有向グラフと無向グラフの簡単な実装例です。

   ```java
   import java.util.ArrayList;
   import java.util.List;

   // グラフのノードを表すクラス
   class GraphNode {
       int value;
       List<GraphNode> neighbors;

       GraphNode(int value) {
           this.value = value;
           neighbors = new ArrayList<>();
       }
   }

   // グラフを表すクラス
   public class Graph {
       List<GraphNode> nodes;

       public Graph() {
           nodes = new ArrayList<>();
       }

       // ノード間にエッジを追加するメソッド
       // このメソッドは、無向グラフと有向グラフで異なる動作をします。
       public void addEdge(GraphNode source, GraphNode target) {
           source.neighbors.add(target); // 有向グラフの場合、この行のみが実行されます。

           // 無向グラフの場合、以下の行も実行され、双方向のエッジが形成されます。
           target.neighbors.add(source);
       }
   }
   ```

   :::
