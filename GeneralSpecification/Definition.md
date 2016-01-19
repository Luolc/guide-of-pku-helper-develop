# 命名

## 分包
统一使用小写，格式为com.pkuhelper.[层级名称].[模块名称]

形如：

- entity
- model
    - impl
- ui
    - [subview_0]
        - impl
    - [subview_1]
- presenter
- manager
- util

## 类

## 布局文件

| Type | Rule | Example |
| -- | -- | -- |
| Activity布局 | activity_[功能模块] | activity_hole |
| Fragment布局 | fragment_[功能模块] | fragment_course_table |
| 列表项 | listitem_[模块] | listitem_hole |
| 包含项 | include_[模块] | include_pkuhelper_content |

#### 控件
| |