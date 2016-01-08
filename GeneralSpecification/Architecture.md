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
| View | 视图层，实现UI更新，当响应用户操作时，调用对应的P来实现逻辑 |
| Manager | 公用方法库，必须被实例化才可以使用 |
| Util | 公用方法库，只包含静态方法，无须实例化 |

## 详解

### Entity
数据实体，一般对应Json包或者ListItem的数据格式。
包括数据的成员变量和相应的Getter，Setter.

例如这是一个典型的Entity




