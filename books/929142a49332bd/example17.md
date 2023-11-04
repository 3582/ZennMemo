---
title: "Type Object Pattern（タイプオブジェクトパターン）"
---
タイプオブジェクトパターンは、オブジェクトのタイプを表すためのオブジェクトを使用するデザインパターンです。これにより、新しいタイプを追加する際に既存のコードを変更することなく、柔軟にシステムを拡張することができます。

**Javaの例**:

```java
// Type abstract class
abstract class AnimalType {
    protected String typeName;
    protected String sound;

    public abstract String getTypeName();
    public abstract String makeSound();
}

// Concrete type classes
class CatType extends AnimalType {
    public CatType() {
        this.typeName = "Cat";
        this.sound = "Meow";
    }

    @Override
    public String getTypeName() {
        return typeName;
    }

    @Override
    public String makeSound() {
        return sound;
    }
}

class DogType extends AnimalType {
    public DogType() {
        this.typeName = "Dog";
        this.sound = "Bark";
    }

    @Override
    public String getTypeName() {
        return typeName;
    }

    @Override
    public String makeSound() {
        return sound;
    }
}

// Main class to demonstrate Type Object Pattern
public class Main {
    public static void main(String[] args) {
        AnimalType catType = new CatType();
        AnimalType dogType = new DogType();

        System.out.println("Animal Type: " + catType.getTypeName() + ", Sound: " + catType.makeSound());
        System.out.println("Animal Type: " + dogType.getTypeName() + ", Sound: " + dogType.makeSound());
    }
}
```

上記の例では、AnimalTypeは動物のタイプを表す抽象クラスです。CatTypeとDogTypeは具体的な動物のタイプを表すクラスで、それぞれ猫と犬の特性を持っています。

このパターンを使用すると、新しい動物のタイプを追加する際に、新しいクラスを作成するだけで、既存のコードを変更することなくシステムを拡張することができます。
