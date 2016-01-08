# 架构
应用采用Model - View - Presenter架构设计，另从Model层中单独分离出Entity数据实体（类似于C++中的一个结构体），只作为数据的实例化存在。

此外，引入Manager和Util层，负责封装全应用范围内的公用方法。

应用包含一个Config接口，用来配置应用的常量。

## 概览
| Layer | Description |
| -- | -- |
| Entity | 数据实体，一般直接对应Json包或者ListItem |
| Modle | 模型层，负责数据的获取和发送（包括网络、本地和缓存） |
| Presenter | 逻辑层，实现应用的业务逻辑 |
| View | 视图层，实现UI更新，当响应用户操作时，调用对应的Presenter来实现逻辑 |
| Manager | 公用方法库，必须被实例化才可以使用 |
| Util | 公用方法库，只包含静态方法，无须实例化 |

## 详解

### Entity
数据实体，一般对应Json包或者ListItem的数据格式。
包括数据的成员变量和相应的Getter，Setter.

例如这是一个典型的Entity
```java
public class HoleListItemEntity {
    private int pid;
    private String text;
    private String type;
    private long timestamp;
    private int reply;
    private int likenum;
    private int extra;
    private String url;
    private long hot;

    // Some Getters and Setters
    // ...
}
```

### Model
模型层，负责数据的获取和发送。包括向服务器网络请求，从本地文件或缓存读写。

由于数据读取的结果不一定成功，为了处理各种状况，我们需要在Model层的方法中提供一个回调接口，在Presenter层实现具体的逻辑。

> 我们约定回调接口定义如下：

> ```java
> public interface Callback<T> {
>
>     void onFinished(int code, T data);
> 
>     void onError(String msg);
> }
> ```



