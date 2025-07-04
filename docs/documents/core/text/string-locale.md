# 本地化

## 中文字符串检查

> 添加：[:octicons-tag-24: Version 0.1.4](https://sakurajimamaii.github.io/AVE-DOC/version/core/#014)

```kotlin
isChinese("你好，世界") // 返回 true
isChinese("你好，世界，這是繁體") // 返回 true
isChinese("Hello World!") // 返回 false
```
