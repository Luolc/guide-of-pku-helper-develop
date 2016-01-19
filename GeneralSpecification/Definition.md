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
大驼峰法命名。

| Class | Rule | Example |
| -- | -- | -- |
| Entity | [DataName]Entity | HoleListItemEntity |
| Model Interface | I[ModelName]Mod | IPkuHoleMod |
| Model Implementation | [ModelName]Mod | PkuHoleMod |
| View Interface | I[ViewName]UI | IPkuHoleUI |
| View Implementation | [ViewName]Activity(Fragment) | PkuHoleActivity, MyPkuFragment |
| View Adapter | [AdapterName]Adapter | HoleListAdapter |
| Presenter | [PresenterName]Presenter | PkuHolePresenter |
| Manager | [ManagerName]Manager | ApiManager |
| Util | [UtilName]Util | TimeUtil |

## 方法
采用动词[名词]格式命名，小驼峰法。

常见的有getXX, setXX, isXX等。

## 变量
### 普通变量
小驼峰法。

在代码块开始处声明。

### 成员变量
非View控件实体的，以m开头，例如mContext.

View控件的实体，以控件缩写开头，例如tvContent(一个TextView).

### 常量
全部大写，以下划线分割，例如TYPE_AUDIO.

## 控件
采用[控件缩写]\_[模块]\_[功能]方式命名。
在java文件中以对应的小驼峰法命名。

| Type | Prefix | Example |
| -- | -- | -- |
| Layout | layout | layout_image |
| TextView | tv | tv_pid |
| ImageView | img | img_reply |
| Button | btn | btn_login |
| EditText | et | et_password |
| ListView | lv | lv_hole |

（待补充）


## 资源文件

### 布局文件

| Type | Rule | Example |
| -- | -- | -- |
| Activity布局 | activity_[功能模块] | activity_hole |
| Fragment布局 | fragment_[功能模块] | fragment_course_table |
| 列表项 | listitem_[模块] | listitem_hole |
| 包含项 | include_[模块] | include_pkuhelper_content |

### drawble