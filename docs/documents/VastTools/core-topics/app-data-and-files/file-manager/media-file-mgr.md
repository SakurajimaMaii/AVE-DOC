# 媒体文件管理

## 获取默认文件名

```kotlin
// 获取 20230313_234940_455_com_ave_vastgui_app.jpg 作为默认文件名
val name = ImageMgr.getDefaultFileName(".jpg")
```

## 通过 Uri 获取媒体文件

`getFileByUri` 会查询给定的 `uri` 的 `DATA` 字段值，如果有则返回对应的文件对象，否则返回空

```kotlin
val file:File? = ImageMgr.getFileByUri(path)
```

## 获取文件 Uri

```kotlin
// 新的媒体文件
val file = File(path, name)
// 获取媒体文件 Uri
uri = file.let {
    if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.R) {
        ImageMgr.getFileUriAboveApi30(it)
    } else if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.N) {
        ImageMgr.getFileUriAboveApi24(it, authority)
    } else {
        ImageMgr.getFileUriOnApi23(it)
    }
}
```

### 对 Android 11 的适配(API 30开始)

!!! warning "关于文件路径的说明"

    对于媒体文件，你应该保存到共享的存储空间。

通过 `getFileUriAboveApi30` ，会调用 `contentResolver.insert()` 方法插入一条新的记录，并将对应的 `Uri` 返回。

### 对 Android 7 的适配(API 24开始)

通过 `getFileUriAboveApi24` ，会调用 `FileProvider.getUriForFile` 方法获取 `Uri` 。

### 对 Android 6 及以下版本的适配

通过 `getFileUriOnApi23` ， 会调用 `Uri.fromFile()` 直接获取 `Uri` 。

## 获取共享存储空间

[:octicons-tag-24: Version 0.5.0](https://ave.entropy2020.cn/version/VastTools/#050)

```kotlin
// 对应路径 /storage/emulated/0/Pictures
val dir = ImageMgr.getSharedFilesDir()
```

## 获取专属存储空间

[:octicons-tag-24: Version 0.5.0](https://ave.entropy2020.cn/version/VastTools/#050)

```kotlin
// 对应路径 /storage/emulated/0/Android/data/com.ave.vastgui.app/files/Pictures
val dir = ImageMgr.getExternalFilesDir()
```