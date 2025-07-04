# Handler 和 HandlerThread 拓展

## LifecycleHandler

> 添加：[:octicons-tag-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

`LifecycleHandler` 会在 `onDestroy` 被回调时调用 `removeCallbacksAndMessages()` 。

```kotlin
val handler by LifecycleHandler()
```

## LifecycleHandler

> 添加：[:octicons-tag-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

`LifecycleHandlerThread` 会在 `onDestroy` 被回调时调用 `quitSafely()` 。

```kotlin
val handler by LifecycleHandlerThread("thread")
```
