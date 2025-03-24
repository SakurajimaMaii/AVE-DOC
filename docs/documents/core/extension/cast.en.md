# Type casts

[:octicons-tag-24: Version 0.0.1](https://sakurajimamaii.github.io/AVE-DOC/version/core/#001)

```kotlin
open class Person(val name:String)

class Student(val grade:Int, val stuName: String):Person(stuName){
    fun hungry(){
        LogUtils.i(stuName,"I'm hungry.")
    }
}

val a = cast<Person>(Student(6,"小明"))
```
