# 获取 activity 的结果

借助工具包提供给你的合约，你可以配合 `registerForActivityResult()`
 API 来快速的获取 activity 结果。

## CropPhotoContract

该合约接收一个 `CropIntent` 类型的参数，并返回裁剪后图片的 `uri` 。

=== "kotlin"

    ```kotlin
    private val cropPicture =
        registerForActivityResult(CropPhotoContract()) {
            val bitmap: Uri = it
                ?: throw RuntimeException("bitmap is null")
            getBinding().image.setImageURI(bitmap)
        }
    ```

=== "java"

    ```java
    private final ActivityResultLauncher<CropIntent> cropPhoto = 
        registerForActivityResult(new CropPhotoContract(), result -> {
            getBinding().image.setImageURI(result);
        }
    ```

### 对 Android 11 的适配(API 30开始)

- 文件保存路径

    裁剪出的照片会被保存在 `Environment.getExternalStoragePublicDirectory(DIRECTORY_PICTURES).path` 下面。

### 对 Android 7 的适配(API 24开始)

- 文件保存路径

    裁剪出的照片会被保存在 `Environment.getExternalStoragePublicDirectory(DIRECTORY_PICTURES).path` 下面。

- FileProvider 配置

    你需要为 `android.support.FILE_PROVIDER_PATHS` 配置以下路径。

    ```xml
    <!-- File named file_paths.xml in xml folder. -->
    <resources>
        <!-- add this line -->
        <external-path name="name_you_define" path="Pictures" />
    </manifest>
    ```

## PickPhotoContract

该合约允许你从相册中选择一张照片，并返回对应的 `uri` 。

=== "kotlin"

    ```kotlin
    private val getImage =
        registerForActivityResult(PickPhotoContract()) { it ->
            it?.apply { cropImage(this) }
        }
    ```

=== "java"

    ```java
    private val choosePicture = 
        registerForActivityResult(PickPhotoContract()) {
            cutImage(it)
        }
    ```

## TakePhotoContract

该合约允许你使用相机拍摄照片，并返回对应的 `uri` 。

=== "kotlin"

    ```kotlin
    private val takePhoto =
        registerForActivityResult(TakePhotoContract()) {
            val bitmap: Uri = it
                ?: throw RuntimeException("bitmap is null")
            getBinding().image.setImageURI(bitmap)
        }
    ```

=== "java"

    ```java
    private val takePicture = 
        registerForActivityResult(TakePhotoContract()) {
            cutImage(it)
        }
    ```

### 对 Android 11 的适配(API 30开始)

- 文件保存路径

    拍摄出的照片会被保存在 `Environment.getExternalStoragePublicDirectory(DIRECTORY_PICTURES).path` 下面。

### 对 Android 7 的适配(API 24开始)

- 文件保存路径

    拍摄出的照片会被保存在 `Environment.getExternalStoragePublicDirectory(DIRECTORY_PICTURES).path` 下面。

- FileProvider 配置

    你需要为 `android.support.FILE_PROVIDER_PATHS` 配置以下路径。

    ```xml
    <!-- File named file_paths.xml in xml folder. -->
    <resources>
        <!-- add this line -->
        <external-path name="name_you_define" path="Pictures" />
    </manifest>
    ```

## GetMediaFileContract 

该合约允许你选择媒体文件中的照片或者视频，并返回对应的 `uri` 。

```kotlin
private val openGalleryLauncher =
    registerForActivityResult(GetMediaFileContract()) {
        getBinding().video.apply {
            setVideoURI(it)
            start()
        }
    }
```
