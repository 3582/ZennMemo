---
title: "Architectural Patterns（アーキテクチャパターン）"
---
1. **MVC (Model-View-Controller)**
   - **説明**: MVCは、アプリケーションのロジックを3つの主要なコンポーネントに分離するデザインパターンです。
   - **Javaの例**:

     ```java
     // Model
     public class User {
         private String name;
         // getters and setters
     }

     // View
     public class UserView {
         public void printUserDetails(String userName) {
             System.out.println("User: " + userName);
         }
     }

     // Controller
     public class UserController {
         private User model;
         private UserView view;

         public UserController(User model, UserView view) {
             this.model = model;
             this.view = view;
         }

         public void setUserName(String name) {
             model.setName(name);
         }

         public void updateView() {
             view.printUserDetails(model.getName());
         }
     }
     ```

2. **Layered Architecture**
   - **説明**: アプリケーションを異なる機能層に分割するデザインパターン。
   - **Javaの例**:

     ```java
     // Data Access Layer
     public class UserDao {
         public User getUser(int userId) {
             // fetch user from the database
         }
     }

     // Business Logic Layer
     public class UserService {
         private UserDao userDao;

         public UserService(UserDao userDao) {
             this.userDao = userDao;
         }

         public User getUserDetails(int userId) {
             return userDao.getUser(userId);
         }
     }

     // Presentation Layer
     public class UserController {
         private UserService userService;

         public UserController(UserService userService) {
             this.userService = userService;
         }

         public void displayUser(int userId) {
             User user = userService.getUserDetails(userId);
             // display user details
         }
     }
     ```

3. **Microservices Architecture**
   - **説明**: アプリケーションを独立した小さなサービスに分割し、それぞれのサービスが独自のデータベースと依存関係を持つデザインパターン。
   - **Javaの例**: このパターンは、Javaの短いコードスニペットで説明するのは難しいですが、Spring BootとSpring Cloudを使用してマイクロサービスを実装することが一般的です。

---

これらのアーキテクチャパターンは、大規模なアプリケーションやシステムの設計において、構造と責任を明確にするためのものです。
