# 类型转换拓展

[:octicons-tag-24: Version 0.0.1](https://ave.entropy2020.cn/version/core/#001)

```kotlin
open class Person(val name:String)

class Student(val grade:Int, val stuName: String):Person(stuName){
    fun hungry(){
        LogUtils.i(stuName,"I'm hungry.")
    }
}

val a = cast<Person>(Student(6,"小明"))
```
