# 下载

!!! note "前言"

    下载工具类是基于 [OKHttp3](https://github.com/square/okhttp) 构建的。

## 快速使用

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

通过 `DLManager` 你可以创建一个下载任务，并为其配置下载链接，保存路径内容。

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

## 断点下载

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

下载任务对象提供了 `pause` ， `resume` 等方法以便暂停任务。

```kotlin
downloadTask.resume()
```

## MD5 验证

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

通过调用 `setMD5` ，你可以设置文件的 MD5 以便进行校验。默认情况下不进行该操作。

```kotlin
downloadTask = DLManager
    ... // 其他设置
    .setMD5("5D41402ABC4B2A76B9719D911017C592")
    .build()
```

## 下载事件监听

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

目前你可以监听以下下载事件：

- 下载成功
- 下载中
- 下载失败
- 下载暂停
- 下载取消
