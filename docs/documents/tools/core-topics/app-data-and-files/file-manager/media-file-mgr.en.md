# Media file management

## Default media file name

Call `getDefaultFileName` to get the file name with the specified suffix.
 
```kotlin
// Return 20230313_234940_455_com_ave_vastgui_app.jpg 
val name = ImageMgr.getDefaultFileName(".jpg")
```

## Access media file by uri

`getFileByUri` will search `DATA` field value of the `uri` ，return the corresponding file, null otherwise.

```kotlin
val file:File? = ImageMgr.getFileByUri(path)
```

## Get media file uri

```kotlin
// Create a file
val file = File(path, name)
// Get media file uri
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

### Compatibility with Android 11(API 30)

!!! warning "Instructions about file paths"

     For media files, you should save to shared storage.

`getFileUriAboveApi30` will call `contentResolver.insert()` to insert a new record and return the corresponding `Uri` .

### Compatibility with Android 7(API 24)

`getFileUriAboveApi24` will use `FileProvider.getUriForFile` to get `Uri` .

### Compatibility with sdk under Android 7

`getFileUriOnApi23` will use `Uri.fromFile()` to get `Uri` 。

## Shared storage

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

```kotlin
// Return /storage/emulated/0/Pictures
val dir = ImageMgr.getSharedFilesDir()
```

## App-specific files

[:octicons-tag-24: Version 0.5.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#050)

```kotlin
// Return /storage/emulated/0/Android/data/com.ave.vastgui.app/files/Pictures
val dir = ImageMgr.getExternalFilesDir()
```