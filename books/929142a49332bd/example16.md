---
title: "Null Object Pattern（ヌルオブジェクトパターン）"
---
ヌルオブジェクトパターンは、nullオブジェクトの代わりに実際のオブジェクトを提供するデザインパターンです。これにより、nullチェックの必要がなくなり、コードがクリーンになります。

**Javaの例**:

```java
// Abstract class
abstract class AbstractCustomer {
    protected String name;
    public abstract boolean isNil();
    public abstract String getName();
}

// Concrete class for real customers
class RealCustomer extends AbstractCustomer {
    public RealCustomer(String name) {
        this.name = name;
    }

    @Override
    public boolean isNil() {
        return false;
    }

    @Override
    public String getName() {
        return name;
    }
}

// Null Object class
class NullCustomer extends AbstractCustomer {
    @Override
    public boolean isNil() {
        return true;
    }

    @Override
    public String getName() {
        return "Not Available";
    }
}

// Customer factory to get real or null customers
class CustomerFactory {
    public static AbstractCustomer getCustomer(String name) {
        if (name.equalsIgnoreCase("John")) {
            return new RealCustomer("John");
        }
        return new NullCustomer();
    }
}

// Main class to demonstrate Null Object Pattern
public class Main {
    public static void main(String[] args) {
        AbstractCustomer customer1 = CustomerFactory.getCustomer("John");
        AbstractCustomer customer2 = CustomerFactory.getCustomer("Mike");

        System.out.println(customer1.getName());  // Outputs: John
        System.out.println(customer2.getName());  // Outputs: Not Available
    }
}
```

上記の例では、AbstractCustomerは顧客を表す抽象クラスです。RealCustomerは実際の顧客を表し、NullCustomerは存在しない顧客を表すヌルオブジェクトです。CustomerFactoryは、指定された名前の顧客が存在する場合はRealCustomerを、存在しない場合はNullCustomerを返します。

このパターンを使用すると、nullチェックを繰り返す代わりに、ヌルオブジェクトが適切なデフォルト動作を提供することで、コードがシンプルになります。
