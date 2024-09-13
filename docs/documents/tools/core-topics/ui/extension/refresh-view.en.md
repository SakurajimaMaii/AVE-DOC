# Refresh view

## refreshWithInvalidate

[:octicons-tag-24: Version 0.2.0](https://ave.entropy2020.cn/version/tools/#020)

`refreshWithInvalidate` will call `View.invalidate` at last.

```kotlin
mBindings.waveProgressView.refreshWithInvalidate {
    setHint("Hello")
    setCurrentProgress(progress.toFloat())
}
```
