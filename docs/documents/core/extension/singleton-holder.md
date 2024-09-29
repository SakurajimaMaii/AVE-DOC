# SingletonHolder

通过 `SingletonHolder` 你可以创建含参单例。

## 快速开始

[:octicons-tag-24: Version 0.0.3](https://ave.entropy2020.cn/version/core/#003)

- 声明类

    ```kotlin
    class Singleton private constructor(name: String) {

        companion object:SingletonHolder<Singleton,String>(::Singleton)

    }
    ```

- 获取单例对象

    ```kotlin
    private val singleton by lazy {
        Singleton.getInstance(defaultLogTag())
    }
    ```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/model/Singleton.kt){ .md-button }
