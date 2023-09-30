# 对话框

!!! info "MaterialAlertDialogBuilder"

    在 [com.google.android.material.dialog.MaterialAlertDialogBuilder](https://m3.material.io/components/dialogs/overview) 的基础上进行了拓展。

## 设置布局

```java
// 创建一个 MaterialAlertDialogBuilder 对象
MaterialAlertDialogBuilder builder = new MaterialAlertDialogBuilder(requireActivity());
// 自定义布局，通过布局 id 获取。
builder.setView(R.layout.dialog_change_info);
```

当然你也可以通过下列方式设置布局

```kotlin
fun setView(view: View?)
fun setView(@LayoutRes layoutId: Int, context: Context,
root: ViewGroup?)
```

## 获取非空布局

```java
View view = builder.requireView();
```

## 查找布局内控件

```java
final EditText changeEditText = builder.findViewById(R.id.change_edit_text);
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/activity/view/DialogActivity.kt){ .md-button }
