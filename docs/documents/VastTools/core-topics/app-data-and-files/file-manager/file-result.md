# 操作结果

[:octicons-tag-24: Version 0.4.0](https://ave.entropy2020.cn/version/VastTools/#040)

## 获取操作结果

`FileResult` 作为文件操作的结果，能让你更好地观察操作结果

```kotlin
val result = moveFile(
    File("${appInternalFilesDir().path}${File.separator}moveDir${File.separator}1.txt"),
    appInternalFilesDir().path
)
```

### 判断操作的结果

- `isSuccess`

    如果操作成功返回 `true` ，否则返回 `false` 。

- `isFailure`

    如果操作失败返回 `true` ，否则返回 `false` 。

### 获取操作结果信息

- `successOrNull()`

    如果操作成功返回成功信息字符串 ，否则为空。

- `exceptionOrNull()`

    如果操作失败返回异常 `Exception` 对象 ，否则为空。