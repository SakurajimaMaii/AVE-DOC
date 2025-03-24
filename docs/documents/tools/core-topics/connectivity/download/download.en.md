# Download

!!! note "Preface"

     The download util is built based on [OKHttp3](https://github.com/square/okhttp).

## Quick start

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

Through `DLManager` you can create a download task, configure the download link for it, or the save path.

```kotlin
downloadTask = DLManager
     .createTaskConfig()
     .setDownloadUrl(downloadUrl)
     .setSaveDir(FileMgr.appInternalFilesDir().path)
     .setListener {
         onDownloading = {
             ... //Do something
         }
         onFailure = {
             ... //Do something
         }
         onSuccess = {
             ... //Do something
         }
     }
     .build()
```

## Breakpoint download

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

The download task object provides `pause`, `resume` and other methods to pause the task.

```kotlin
downloadTask. resume()
```

## MD5 verification

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

By calling `setMD5`, you can set the MD5 of the file for verification. This is not done by default.

```kotlin
downloadTask = DLManager
     ... // other settings
     .setMD5("5D41402ABC4B2A76B9719D911017C592")
     .build()
```

## Download event listener

[:octicons-tag-24: Version 0.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#052)

Currently you can listen for the following download events:

- download successful
- downloading
- download failed
- Download paused
- download cancel
