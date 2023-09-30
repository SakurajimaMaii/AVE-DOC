# Get string with unit

## Quick start

The following are the units provided by default.

|   Unit    | Unit Value |
| :-------: | :--------: |
|   Angle   |    39°     |
|  Celsius  |    36℃     |
|    Kmh    |   2km/h    |
| Kilometer |    2km     |
|   Meter   |     2m     |
|    Ms     |    2m/s    |
|  Percent  |    77％    |

[:octicons-tag-24: Version 0.5.1](https://ave.entropy2020.cn/version/VastTools/#051)

=== "kotlin"

    ```kotlin
    // Get value as 12km/h
    @Composable
    fun UnitString(){
        Text(text = "12".withUnit(Kmh()))
    }
    ```

=== "java"

    ```java
    UnitStringKt.withUnit(1, new Angle());
    ```

## Custom unit

[:octicons-tag-24: Version 0.5.2](https://ave.entropy2020.cn/version/VastTools/#052)

By implementing `StrUnit` you can customize the unit:

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

## Sample code

[Sample Code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/java/com/ave/vastgui/appcompose/example/text/UnitString.kt){ .md-button }
