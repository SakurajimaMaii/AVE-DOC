# SpEncrypted

`SpEncrypted` 用于打开加密的 SharedPreferences 实例。

## 快速开始

```kotlin
// 声明您自己的 SharedPreferences 。
class EncryptedSp(name: String) {

    // 通过 SpEncrypted.getInstance() 获取 SharedPreferences 实例。
    private val sp by lazy{
        SpEncrypted.getInstance(name).getSharedPreferences()
    }

    // 声明变量。
    var count by sp.float()

}

// 创建 EncryptedSp 。
private val mSp by lazy { EncryptedSp(defaultLogTag()) }

// 设置值。
mSp.count = 1f
// 获取值。
val count = mSp.count
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/sharedpreferences/SpEncryptedExample.kt){ .md-button }
