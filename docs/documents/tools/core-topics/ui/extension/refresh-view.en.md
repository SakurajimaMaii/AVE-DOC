# Refresh view

## refreshWithInvalidate

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

`refreshWithInvalidate` will call `View.invalidate` at last.

```kotlin
mBindings.waveProgressView.refreshWithInvalidate {
    setHint("Hello")
    setCurrentProgress(progress.toFloat())
}
```
