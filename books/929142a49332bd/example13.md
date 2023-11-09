---
title: "GoF Design Patterns（GoFデザインパターン）"
---
1. **Creational Patterns（生成パターン）**
   - Singleton（シングルトン）
   - Factory Method（ファクトリメソッド）
   - Abstract Factory（抽象ファクトリ）
   - Builder（ビルダー）
   - Prototype（プロトタイプ）

:::details Creational Patterns（生成パターン）
   生成パターンは、オブジェクトの作成方法に関するデザインパターンです。これにより、システムが具体的なクラスに依存せずにオブジェクトを作成できるようになります。

   1. **Singleton（シングルトン）**
      - **説明**: シングルトンパターンは、クラスのインスタンスが1つだけ存在することを保証するデザインパターンです。
      - **Javaの例**:

      ```java
      public class Singleton {
            private static Singleton instance;

            private Singleton() {}

            public static synchronized Singleton getInstance() {
               if (instance == null) {
                  instance = new Singleton();
               }
               return instance;
            }
      }
      ```

   2. **Factory Method（ファクトリメソッド）**
      - **説明**: ファクトリメソッドパターンは、サブクラスがインスタンス化するクラスを決定するデザインパターンです。
      - **Javaの例**:

      ```java
      interface Product {
            void create();
      }

      class ConcreteProductA implements Product {
            public void create() {
               System.out.println("Product A");
            }
      }

      class ConcreteProductB implements Product {
            public void create() {
               System.out.println("Product B");
            }
      }

      abstract class Creator {
            public abstract Product factoryMethod();
      }

      class ConcreteCreatorA extends Creator {
            public Product factoryMethod() {
               return new ConcreteProductA();
            }
      }

      class ConcreteCreatorB extends Creator {
            public Product factoryMethod() {
               return new ConcreteProductB();
            }
      }
      ```

   3. **Abstract Factory（抽象ファクトリ）**
      - **説明**: 抽象ファクトリパターンは、関連するオブジェクトのグループを作成するインターフェースを提供するデザインパターンです。
      - **Javaの例**:

      ```java
      interface Button {
            void paint();
      }

      class WinButton implements Button {
            public void paint() {
               System.out.println("Windows Button");
            }
      }

      class MacButton implements Button {
            public void paint() {
               System.out.println("Mac Button");
            }
      }

      interface GUIFactory {
            Button createButton();
      }

      class WinFactory implements GUIFactory {
            public Button createButton() {
               return new WinButton();
            }
      }

      class MacFactory implements GUIFactory {
            public Button createButton() {
               return new MacButton();
            }
      }
      ```

   4. **Builder（ビルダー）**
      - **説明**: ビルダーパターンは、複雑なオブジェクトの作成を簡素化するデザインパターンです。
      - **Javaの例**:

      ```java
      class Computer {
            private String HDD;
            private String RAM;

            private Computer(Builder builder) {
               this.HDD = builder.HDD;
               this.RAM = builder.RAM;
            }

            public static class Builder {
               private String HDD;
               private String RAM;

               public Builder setHDD(String HDD) {
                  this.HDD = HDD;
                  return this;
               }

               public Builder setRAM(String RAM) {
                  this.RAM = RAM;
                  return this;
               }

               public Computer build() {
                  return new Computer(this);
               }
            }
      }
      ```

   5. **Prototype（プロトタイプ）**
      - **説明**: プロトタイプパターンは、既存のオブジェクトをコピーして新しいオブジェクトを作成するデザインパターンです。
      - **Javaの例**:

      ```java
      class Prototype implements Cloneable {
            public Prototype clone() {
               try {
                  return (Prototype) super.clone();
               } catch (CloneNotSupportedException e) {
                  e.printStackTrace();
                  return null;
               }
            }
      }
      ```

   ---

   これらの生成パターンは、オブジェクトの作成とクラスの実際の実装の分離を助けることで、コードの再利用性と柔軟性を向上させます。

:::

2. **Structural Patterns（構造パターン）**
   - Adapter（アダプター）
   - Bridge（ブリッジ）
   - Composite（コンポジット）
   - Decorator（デコレータ）
   - Facade（ファサード）
   - Flyweight（フライウェイト）
   - Proxy（プロキシ）

:::details Structural Patterns（構造パターン）※抜粋
   構造パターンは、オブジェクトやクラスの構成方法に関するデザインパターンです。これにより、大きな構造を形成するための新しい方法を提供します。

   1. **Adapter（アダプター）**
      - **説明**: アダプターパターンは、既存のクラスのインターフェースを新しいインターフェースに変換するデザインパターンです。
      - **Javaの例**:

      ```java
      interface OldInterface {
            void oldMethod();
      }

      class OldClass implements OldInterface {
            public void oldMethod() {
               System.out.println("Old method");
            }
      }

      interface NewInterface {
            void newMethod();
      }

      class Adapter implements NewInterface {
            private OldInterface oldObject;

            public Adapter(OldInterface oldObject) {
               this.oldObject = oldObject;
            }

            public void newMethod() {
               oldObject.oldMethod();
            }
      }
      ```

   2. **Bridge（ブリッジ）**
      - **説明**: ブリッジパターンは、実装から抽象を分離するデザインパターンです。
      - **Javaの例**:

      ```java
      interface Color {
            void applyColor();
      }

      class RedColor implements Color {
            public void applyColor() {
               System.out.println("Red color");
            }
      }

      abstract class Shape {
            protected Color color;

            public Shape(Color color) {
               this.color = color;
            }

            abstract void draw();
      }

      class Circle extends Shape {
            public Circle(Color color) {
               super(color);
            }

            public void draw() {
               System.out.print("Circle drawn with ");
               color.applyColor();
            }
      }
      ```

   3. **Composite（コンポジット）**
      - **説明**: コンポジットパターンは、オブジェクトを木構造で構成し、個々のオブジェクトとその組み合わせを均等に扱うデザインパターンです。
      - **Javaの例**:

      ```java
      interface Component {
            void show();
      }

      class Leaf implements Component {
            private String name;

            public Leaf(String name) {
               this.name = name;
            }

            public void show() {
               System.out.println(name);
            }
      }

      class Composite implements Component {
            private List<Component> components = new ArrayList<>();

            public void add(Component component) {
               components.add(component);
            }

            public void show() {
               for (Component component : components) {
                  component.show();
               }
            }
      }
      ```

   4. **Decorator（デコレーター）**
      - **説明**: デコレーターパターンは、オブジェクトに動的に新しい責任を追加するデザインパターンです。
      - **Javaの例**:

      ```java
      interface Coffee {
            double cost();
      }

      class SimpleCoffee implements Coffee {
            public double cost() {
               return 5;
            }
      }

      class MilkDecorator implements Coffee {
            private Coffee coffee;

            public MilkDecorator(Coffee coffee) {
               this.coffee = coffee;
            }

            public double cost() {
               return coffee.cost() + 2;
            }
      }
      ```

   5. **Proxy（プロキシ）**
      - **説明**: プロキシパターンは、他のオブジェクトへのアクセスを制御するための代理オブジェクトを提供するデザインパターンです。
      - **Javaの例**:

      ```java
      interface Image {
            void display();
      }

      class RealImage implements Image {
            private String filename;

            public RealImage(String filename) {
               this.filename = filename;
               loadFromDisk();
            }

            private void loadFromDisk() {
               System.out.println("Loading " + filename);
            }

            public void display() {
               System.out.println("Displaying " + filename);
            }
      }

      class ProxyImage implements Image {
            private RealImage realImage;
            private String filename;

            public ProxyImage(String filename) {
               this.filename = filename;
            }

            public void display() {
               if (realImage == null) {
                  realImage = new RealImage(filename);
               }
               realImage.display();
            }
      }
      ```

   ---

   これらの構造パターンは、オブジェクトやクラスの構成方法を簡素化し、柔軟性を向上させることを目的としています。

:::

3. **Behavioral Patterns（振る舞いパターン）**
   - Chain of Responsibility（責任連鎖）
   - Command（コマンド）
   - Interpreter（インタープリタ）
   - Iterator（イテレータ）
   - Mediator（メディエータ）
   - Memento（メメント）
   - Observer（オブザーバ）
   - State（ステート）
   - Strategy（ストラテジー）
   - Template Method（テンプレートメソッド）
   - Visitor（ビジター）

:::details Behavioral Patterns（振る舞いパターン）※抜粋
   振る舞いパターンは、オブジェクト間の共通のコミュニケーションパターンを識別し、これらのパターンを最大限に活用することを目的としています。

   1. **Observer（オブザーバー）**
      - **説明**: オブザーバーパターンは、オブジェクトの状態が変わったときに他のオブジェクトに自動的に通知するデザインパターンです。
      - **Javaの例**:

      ```java
      interface Observer {
            void update(String message);
      }

      interface Subject {
            void registerObserver(Observer observer);
            void removeObserver(Observer observer);
            void notifyObservers();
      }

      class ConcreteSubject implements Subject {
            private List<Observer> observers = new ArrayList<>();
            private String message;

            public void setMessage(String message) {
               this.message = message;
               notifyObservers();
            }

            public void registerObserver(Observer observer) {
               observers.add(observer);
            }

            public void removeObserver(Observer observer) {
               observers.remove(observer);
            }

            public void notifyObservers() {
               for (Observer observer : observers) {
                  observer.update(message);
               }
            }
      }

      class ConcreteObserver implements Observer {
            private String name;

            public ConcreteObserver(String name) {
               this.name = name;
            }

            public void update(String message) {
               System.out.println(name + " received message: " + message);
            }
      }
      ```

   2. **Strategy（ストラテジー）**
      - **説明**: ストラテジーパターンは、アルゴリズムのセットを定義し、それぞれをカプセル化して、それらを相互に交換可能にするデザインパターンです。
      - **Javaの例**:

      ```java
      interface Strategy {
            int doOperation(int num1, int num2);
      }

      class OperationAdd implements Strategy {
            public int doOperation(int num1, int num2) {
               return num1 + num2;
            }
      }

      class OperationSubtract implements Strategy {
            public int doOperation(int num1, int num2) {
               return num1 - num2;
            }
      }

      class Context {
            private Strategy strategy;

            public Context(Strategy strategy) {
               this.strategy = strategy;
            }

            public int executeStrategy(int num1, int num2) {
               return strategy.doOperation(num1, num2);
            }
      }
      ```

   3. **State（ステート）**
      - **説明**: ステートパターンは、オブジェクトの内部状態が変わったときにオブジェクトの振る舞いを変更するデザインパターンです。
      - **Javaの例**:

      ```java
      interface State {
            void doAction(Context context);
      }

      class StartState implements State {
            public void doAction(Context context) {
               System.out.println("Player is in start state");
               context.setState(this);
            }

            public String toString() {
               return "Start State";
            }
      }

      class StopState implements State {
            public void doAction(Context context) {
               System.out.println("Player is in stop state");
               context.setState(this);
            }

            public String toString() {
               return "Stop State";
            }
      }

      class Context {
            private State state;

            public Context() {
               state = null;
            }

            public void setState(State state) {
               this.state = state;
            }

            public State getState() {
               return state;
            }
      }
      ```

   4. **Command（コマンド）**
      - **説明**: コマンドパターンは、要求をオブジェクトとしてカプセル化し、クライアントを異なる要求、キュー、またはログ要求をサポートするオブジェクトと分離するデザインパターンです。
      - **Javaの例**:

      ```java
      interface Command {
            void execute();
      }

      class Light {
            public void on() {
               System.out.println("Light is ON");
            }

            public void off() {
               System.out.println("Light is OFF");
            }
      }

      class LightOnCommand implements Command {
            private Light light;

            public LightOnCommand(Light light) {
               this.light = light;
            }

            public void execute() {
               light.on();
            }
      }

      class LightOffCommand implements Command {
            private Light light;

            public LightOffCommand(Light light) {
               this.light = light;
            }

            public void execute() {
               light.off();
            }
      }

      class RemoteControl {
            private Command command;

            public void setCommand(Command command) {
               this.command = command;
            }

            public void pressButton() {
               command.execute();
            }
      }
      ```

   ---

   これらの振る舞いパターンは、オブジェクト間の相互作用を簡素化し、柔軟性を向上させることを目的としています。

:::
