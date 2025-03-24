# 拓展方法

## 概述

我们知道有时候你的 `Fragment` 已经有继承对象，因此对你而言继承 `VastFragment` 组件显然是不合适的，因而你可以使用下面的方法来拓展其功能。

## 获取 ViewBinding

请参考 [获取ViewBinding](https://sakurajimamaii.github.io/AVE-DOC/documents/VastTools/architecture-components/ui-layer-libraries/view-bind/vb-reflection/#viewbinding)

## 获取类名为默认日志 tag

```kotlin
private val mLogTag = defaultLogTag()
```
