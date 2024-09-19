# Json 格式化

[:octicons-tag-24: Version 1.3.1](https://ave.entropy2020.cn/version/log-core/#131)

默认情况下，如果直接将**对象**作为日志打印内容，则会出现以下错误：

```kotlin
logCat.d(address)
```

> Can not convert class com.log.vastgui.core.model.Address, 
> please install a specific converter plugin.

[LogJson](https://api.ave.entropy2020.cn/log/core/com.log.vastgui.core.plugin/-log-json/index.html) 允许你将对象以 json 的形式打印：

```kotlin
val gson = GsonConverter.getInstance(true)

val logFactory: LogFactory = getLogFactory {
    ...
    install(LogJson) {
        converter = gson
    }
}
```

以下是成功打印示例：

```
╔════════════════════════════════════════════════════════════════════════════════════════════════════
║ Thread: Test worker Tag: LogCatTest Level: DEBUG Time: 2024-06-27 15:23:15
╟────────────────────────────────────────────────────────────────────────────────────────────────────
║ com.log.vastgui.core.LogCatTest.log(LogCatTest.kt:115)
╟────────────────────────────────────────────────────────────────────────────────────────────────────
║ {
║   "id": 1,
║   "name": "Alice Smith",
║   "email": "alice.smith@example.com",
║   "registrationDate": "Jun 27, 2024, 3:23:15 PM",
║   "isActive": true
║ }
╚════════════════════════════════════════════════════════════════════════════════════════════════════
```

目前提供了以下三种 Json 序列化对象

|       类名        |                           属性                            |
| :---------------: | :-------------------------------------------------------: |
| FastJsonConverter | 基于 [FastJson](https://github.com/alibaba/fastjson2) 打造 |
|   GsonConverter   |     基于 [Gson](https://github.com/google/gson) 打造      |
| JacksonConverter  | 基于 [Jackson](https://github.com/FasterXML/jackson) 打造 |
