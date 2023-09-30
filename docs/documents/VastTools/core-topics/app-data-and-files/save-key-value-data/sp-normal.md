# SpNormal

!!! tip 

    出于安全方面的考虑，我更推荐使用 `SpEncrypted` 。

`SpNormal` 用于打开 SharedPreferences 实例。

## 快速开始

```kotlin
// 声明您自己的 SharedPreferences 。
class NormalSp(name: String) {

    // 通过 SpNormal.getInstance() 获取 SharedPreferences 实例。
    private val sp by lazy{
        SpNormal.getInstance(name).getSharedPreferences()
    }

    // 声明变量。
    var count by sp.float()

}

// 创建 NormalSp 。
private val mSp by lazy { NormalSp(defaultLogTag()) }

// 设置值。
mSp.count = 1f
// 获取值。
val count = mSp.count
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/sharedpreferences/SpNormalExample.kt){ .md-button }
