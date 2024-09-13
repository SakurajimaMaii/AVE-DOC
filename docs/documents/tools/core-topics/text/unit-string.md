# 获取带单位的字符串

## 快速使用

目前支持下列单位：

|  单位   |  值   |
| :-----: | :---: |
|  角度   |  39°  |
| 摄氏度  |  36℃  |
| 千米/时 | 2km/h |
|  千米   |  2km  |
|   米    |  2m   |
|  米/秒  | 2m/s  |
| 百分比  | 77％  |

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/tools/#051)

=== "kotlin"

    ```kotlin
    // 获取千米单位数值
    @Composable
    fun UnitString(){
        Text(text = "12".withUnit(Kmh()))
    }
    ```

=== "java"

    ```java
    UnitStringKt.withUnit(1, new Angle());
    ```

## 自定义单位

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/tools/#052)

通过继承 `StrUnit` 你可以自定义单位：

=== "kotlin"

    ```kotlin
    open class Percent : StrUnit {
        override val unit = "%"
    }
    ```

=== "java"


    ```java
    class WindSpeed implements StrUnit {
        @NonNull
        @Override
        public String getUnit() {
            return "m/s";
        }

        @NonNull
        @Override
        public String getValue(@NonNull String value) {
            return value + getUnit();
        }
    }
    ```

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/kotlin/com/ave/vastgui/appcompose/example/text/UnitString.kt){ .md-button }
