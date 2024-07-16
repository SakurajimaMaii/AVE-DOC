# 消息框概览

`SimpleToast` 可以在一个小型弹出式窗口中提供与操作有关的简单反馈。它只会填充消息所需的空间大小，并且当前 activity 会一直显示及供用户与之互动。超时后，消息框会自动消失。

<figure markdown>
  ![Toast](../img/toast.png){ width="400" }
  <figcaption>Toast</figcaption>
</figure>

## 弹出长Toast

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

=== "Kotlin"

    ```kotlin
    SimpleToast.showLongMsg("Hello", this@MainActivity) // 直接使用字符
    SimpleToast.showLongMsg(R.string.app_name, this@MainActivity) // 使用str id
    ```

=== "Java"

    ```java
    SimpleToast.showLongMsg("Hello", this@MainActivity) // 直接使用字符
    SimpleToast.showLongMsg(R.string.app_name, this@MainActivity) // 使用str id
    ```

## 弹出短Toast

[:octicons-tag-24: Version 0.5.3](https://ave.entropy2020.cn/version/VastTools/#053)

=== "Kotlin"

    ```kotlin
    SimpleToast.showShortMsg("Hello", this@MainActivity) // 直接使用字符
    SimpleToast.showShortMsg(R.string.app_name, this@MainActivity) // 使用str id
    ```

=== "Java"

    ```java
    SimpleToast.showShortMsg("Hello", this@MainActivity) // 直接使用字符
    SimpleToast.showShortMsg(R.string.app_name, this@MainActivity) // 使用str id
    ```
