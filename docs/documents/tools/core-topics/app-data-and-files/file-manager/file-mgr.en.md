# App file management

## File path

![File path](../img/device_path.png){ align=right width="250" }

As shown in the picture on the right, the corresponding file paths are displayed in sequence.

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

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/kotlin/com/ave/vastgui/appcompose/example/FilePath.kt){ .md-button }

## File operations

- Using `saveFile` function to save file

    ```kotlin
    saveFile(File(appInternalFilesDir().path, "save.txt"))
    ```

- Get the operation result

    [:octicons-tag-24: Version 0.4.0](https://ave.entropy2020.cn/version/tools/#040)

    ```kotlin
    val result = saveFile(File(appInternalFilesDir().path, "save.txt"))
    if(result.isSuccess){
        .. // Code
    } else {
        .. // Code
    }
    ```

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/FileActivity.kt){ .md-button }

## Build file path

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/tools/#051)

```kotlin
// return a/b/c
val path = FileMgr.getPath { 
    "a" f "b" f "c"
}
```

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/kotlin/com/ave/vastgui/appcompose/example/FilePath.kt){ .md-button }
