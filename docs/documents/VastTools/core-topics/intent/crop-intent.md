# 裁剪照片

`CropIntent` 允许你快速构建裁剪照片的 Intent 。输出格式为 `jpg` 。

!!! tip "CropIntent 和 CropPhotoContract"

    建议配合 [CropPhotoContract](https://ave.entropy2020.cn/documents/VastTools/app-entry-points/activities/ActivityResult/#cropphotocontract) 使用

## 快速使用

### 注册 Activity 获取裁剪结果

```kotlin
private val cropIntentLauncher =
    registerForActivityResult(ActivityResultContracts.StartActivityForResult()) { res ->
        val uri = res.data?.data ?: return@registerForActivityResult
        getBinding().image.setImageURI(uri)
    }
```

### 获取输出文件 Uri

你可以点击 [ImageMgr](https://ave.entropy2020.cn/documents/VastTools/core-topics/app-data-and-files/file-manager/media-file-mgr/) 来了解如何在不同版本下获取文件对应的 Uri 。
 
```kotlin
// 获取输出 uri
val dir = ImageMgr.getExternalFilesDir(null)
val name = ImageMgr.getDefaultFileName(".jpg")
output = ImageMgr.getFileUriAboveApi30(File(dir, name))
```

### 配置裁剪参数并启动 Intent

```kotlin
// 设置相关参数
val cropIntent = CropIntent()
    .setData(uri)
    .setCorp(true)
    .setAspect(1, 1)
    .setOutput(200, 200)
    .setReturnData(false)
    .setNoFaceDetection(true)
    .setOutputUri(output)
    .getIntent()
cropIntentLauncher.launch(cropIntent)
```

## 配合 CropPhotoContract

下面的示例为你展示了如何配合 `CropPhotoContract` 使用。在此情况下无需调用 `getIntent` 和 `setOutputUri` 方法。

=== "Android-View"

    ```kotlin
    // 获取裁剪后的图片并展示
    private val cropIntentLauncher =
        registerForActivityResult(CropPhotoContract()) { uri ->
            uri?.let {
                getBinding().image.setImageURI(it)
            }
        }

    // 构建 CropIntent
    val cropIntent = CropIntent()
        .setData(uri)
        .setCorp(true)
        .setAspect(1, 1)
        .setOutput(200, 200)
        .setReturnData(false)
        .setOutputName(null)
        .setNoFaceDetection(true)
    cropIntentLauncher.launch(cropIntent)
    ```

=== "Compose"

    ```kotlin
    // 获取裁剪后的图片并展示
    val cropIntentLauncher = rememberLauncherForActivityResult(CropPhotoContract()) { uri: Uri? ->
        image = uri
    }

    // 构建 CropIntent
    val cropIntent = CropIntent()
        .setData(it)
        .setCorp(true)
        .setAspect(1, 1)
        .setOutput(200, 200)
        .setReturnData(false)
        .setNoFaceDetection(true)
    cropIntentLauncher.launch(cropIntent)

    // 展示图像
    image?.let { it ->
        AsyncImage(
            model = ImageRequest.Builder(LocalContext.current).data(it).build(),
            contentDescription = null,
            modifier = Modifier.size(200.dp,200.dp)
        )
    }
    ```

## 设置输出图像名称

[:octicons-tag-24: Version 0.4.0](https://ave.entropy2020.cn/version/VastTools/#040)

调用 `setOutputName` 来设置图像名称，如果不设置则使用 [默认值](https://doc.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.manager.mediafilemgr/-media-file-mgr/get-default-file-name.html) 。

```kotlin
val cropIntent = CropIntent()
    ... // 其他设置
    .setOutputName("Name defined by yourself.")
    .getIntent()
```

## 关于 Uri 权限

[:octicons-tag-24: Version 0.4.0](https://ave.entropy2020.cn/version/VastTools/#040)

!!! danger "Uri 权限"

    因为在 `setOutputUri` 会为指定的 `uri` 授予权限，因此你需要在合适的时刻调用 `Coontext.revokeUriPermission` 移除。该操作是为了解决手机显示照片保存失败的问题。 如果使用 `CropPhotoContract` ，则不需要进行该操作。

```kotlin
// 取消 outputUri 权限 
ContextHelper.getAppContext()
    .revokeUriPermission(outputUri, Intent.FLAG_GRANT_WRITE_URI_PERMISSION or Intent.FLAG_GRANT_READ_URI_PERMISSION)
```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/libraries/VastTools/src/main/kotlin/com/ave/vastgui/tools/utils/cropimage){ .md-button }
