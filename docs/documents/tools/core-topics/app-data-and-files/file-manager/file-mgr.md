# 应用文件管理

## 应用专属文件路径

![应用文件路径](../img/device_path.png){ align=right width="250" }

如右图所示，依次展示了对应应用专属文件路径。

```kotlin
private val devicePath = listOf(
    appInternalFilesDir().path,
    appInternalCacheDir().path,
    appExternalFilesDir(null).path,
    appExternalCacheDir().path,
    ImageMgr.getExternalFilesDir().path,
    ImageMgr.getSharedFilesDir().path,
    MusicMgr.getExternalFilesDir().path,
    MusicMgr.getSharedFilesDir().path
)

@Composable
fun DevicePath(modifier: Modifier = Modifier){
    LazyColumn(modifier = modifier){
        items(devicePath){
            ListItem(
                headlineText = { 
                    Text(text = it) 
                }
            )
        }
    }
}
```

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/kotlin/com/ave/vastgui/appcompose/example/FilePath.kt){ .md-button }

## 对文件进行操作

在这里以保存文件作为示例。

### 调用 saveFile 保存文件

```kotlin
saveFile(File(appInternalFilesDir().path, "save.txt"))
```

### 观察操作结果

[:octicons-tag-24: Version 0.4.0](https://ave.entropy2020.cn/version/tools/#040)

```kotlin
val result = saveFile(File(appInternalFilesDir().path, "save.txt"))
if(result.isSuccess){
    .. // 当操作执行成功
} else {
    .. // 当操作失败
}
```

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/FileActivity.kt){ .md-button }

## 构建文件路径

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/tools/#051)

```kotlin
// return a/b/c
val path = FileMgr.getPath { 
    "a" f "b" f "c"
}
```

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/kotlin/com/ave/vastgui/appcompose/example/FilePath.kt){ .md-button }
