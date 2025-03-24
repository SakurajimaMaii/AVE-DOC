# Toast Overview

`SimpleToast` provides simple feedback about an operation in a small popup. It only fills the amount of space required for the message and the current activity remains visible and interactive. Toasts automatically disappear after a timeout.

<figure markdown>
  ![Toast](../img/toast.png){ width="400" }
  <figcaption>Toast</figcaption>
</figure>

## Long Toast

[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053)

!!! note "Long toast"

    === "Kotlin"

        ```kotlin
        SimpleToast.showLongMsg("Hello", this@MainActivity) // use characters directly
        SimpleToast.showLongMsg(R.string.app_name, this@MainActivity) // use str id
        ```

    === "Java"

        ```java
        SimpleToast.showLongMsg("Hello", this@MainActivity) // use characters directly
        SimpleToast.showLongMsg(R.string.app_name, this@MainActivity) // use str id
        ```

## Short Toast

[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053)

!!! note "Short toast"

    === "Kotlin"

        ```kotlin
        SimpleToast.showShortMsg("Hello", this@MainActivity) // use characters directly
        SimpleToast.showShortMsg(R.string.app_name, this@MainActivity) // use str id
        ```

    === "Java"

        ```java
        SimpleToast.showShortMsg("Hello", this@MainActivity) // use characters directly
        SimpleToast.showShortMsg(R.string.app_name, this@MainActivity) // use str id
        ```
