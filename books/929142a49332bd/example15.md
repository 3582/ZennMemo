---
title: "Dependency Injection（依存性の注入）"
---
依存性の注入は、オブジェクトが他のオブジェクトに依存する場合に、その依存関係を外部から注入するテクニックです。これにより、コードの再利用性とテストの容易性が向上します。依存性の注入は、特にSpringフレームワークなどのモダンなフレームワークで一般的に使用されます。

**Javaの例**:

```java
// Service Interface
public interface MessageService {
    void sendMessage(String msg, String recipient);
}

// Email implementation of Service Interface
public class EmailServiceImpl implements MessageService {
    @Override
    public void sendMessage(String msg, String recipient) {
        // Logic to send an email
        System.out.println("Email sent to " + recipient + " with message: " + msg);
    }
}

// Class which depends on MessageService
public class MessageProcessor {
    private MessageService messageService;

    // Constructor-based Dependency Injection
    public MessageProcessor(MessageService messageService) {
        this.messageService = messageService;
    }

    public void processMessage(String message, String recipient) {
        // Some processing with the message
        messageService.sendMessage(message, recipient);
    }
}

// Main class to demonstrate Dependency Injection
public class Main {
    public static void main(String[] args) {
        MessageService emailService = new EmailServiceImpl();
        MessageProcessor processor = new MessageProcessor(emailService);
        processor.processMessage("Hello Dependency Injection", "recipient@example.com");
    }
}
```

上記の例では、MessageProcessorクラスはMessageServiceインターフェースに依存しています。EmailServiceImplはこのインターフェースの実装の一つです。MessageProcessorのインスタンスを作成する際に、具体的なMessageServiceの実装をコンストラクタを通じて注入しています。これにより、後で異なるMessageServiceの実装を簡単に交換することができます。

この方法により、コードの柔軟性が向上し、テストや再利用が容易になります。
