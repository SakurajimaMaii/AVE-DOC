# 控件刷新

## refreshWithInvalidate

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/tools/#020)

通过 `refreshWithInvalidate` ，你可以设置控件的一系列属性，该方法会在最后调用 `View.invalidate` 使得你的设置能够生效。

```kotlin
mBindings.waveProgressView.refreshWithInvalidate {
    setHint("Hello")
    setCurrentProgress(progress.toFloat())
}
```
