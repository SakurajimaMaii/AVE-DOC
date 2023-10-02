# Crop intent

## Quick start

### Register for activity result of crop picture

```kotlin
private val cropIntentLauncher =
    registerForActivityResult(ActivityResultContracts.StartActivityForResult()) { res ->
        val uri = res.data?.data ?: return@registerForActivityResult
        getBinding().image.setImageURI(uri)
    }
```

### Get uri for output picture

Click [ImageMgr](https://ave.entropy2020.cn/documents/VastTools/core-topics/app-data-and-files/file-manager/media-file-mgr/) to learn about how to get the uri with different android version.
 
```kotlin
val dir = ImageMgr.getExternalFilesDir(null)
val name = ImageMgr.getDefaultFileName(".jpg")
output = ImageMgr.getFileUriAboveApi30(File(dir, name))
```

### Configure and start CropIntent

```kotlin
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

## Use CropIntent with CropPhotoContract

The following example shows how to use `CropIntent` with `CropPhotoContract`.

!!! note

    It's necessary to call `getIntent` and `setOutputUri`.

=== "Android-View"

    ```kotlin
    // Get the cropped picture and display it
    private val cropIntentLauncher =
        registerForActivityResult(CropPhotoContract()) { uri ->
            uri?.let {
                getBinding().image.setImageURI(it)
            }
        }

    // Configure CropIntent
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
    // Get the cropped picture and display it
    val cropIntentLauncher = rememberLauncherForActivityResult(CropPhotoContract()) { uri: Uri? ->
        image = uri
    }

    // Configure CropIntent
    val cropIntent = CropIntent()
        .setData(it)
        .setCorp(true)
        .setAspect(1, 1)
        .setOutput(200, 200)
        .setReturnData(false)
        .setNoFaceDetection(true)
    cropIntentLauncher.launch(cropIntent)

    image?.let { it ->
        AsyncImage(
            model = ImageRequest.Builder(LocalContext.current).data(it).build(),
            contentDescription = null,
            modifier = Modifier.size(200.dp,200.dp)
        )
    }
    ```

## Set output picture name

[:octicons-tag-24: Version 0.4.0](https://ave.entropy2020.cn/version/VastTools/#040)

Call `setOutputName` to set output picture name，or take [value](https://doc.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.manager.mediafilemgr/-media-file-mgr/get-default-file-name.html) as the default value.

```kotlin
val cropIntent = CropIntent()
    ... // Other setting
    .setOutputName("Name defined by yourself.")
    .getIntent()
```

## Uri permission

[:octicons-tag-24: Version 0.4.0](https://ave.entropy2020.cn/version/VastTools/#040)

!!! danger "Uri permission"

    Because permission is granted to the specified uri in `setOutputUri`, you need to call `Context.revokeUriPermission` at the appropriate moment to cancel it. This operation is to solve the problem that the mobile phone shows that the photo saving fails. **This is not required if using `CropPhotoContract`** .

```kotlin
// Cancel permission of outputUri 
ContextHelper.getAppContext()
    .revokeUriPermission(outputUri, Intent.FLAG_GRANT_WRITE_URI_PERMISSION or Intent.FLAG_GRANT_READ_URI_PERMISSION)
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/tree/develop/libraries/VastTools/src/main/kotlin/com/ave/vastgui/tools/utils/cropimage){ .md-button }
