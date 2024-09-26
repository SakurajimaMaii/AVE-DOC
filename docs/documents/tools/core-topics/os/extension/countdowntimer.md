# 倒计时

## 倒计时拓展

[:octicons-tag-24: Version 1.2.1](https://ave.entropy2020.cn/version/tools/#121)

通常获取倒计时需要编写以下代码：

```kotlin
val mCDT = object : CountDownTimer(30000, 1000) {
    override fun onTick(millisUntilFinished: Long) {
        mTextField.setText("seconds remaining: " + millisUntilFinished / 1000)
    }

    override fun onFinish() {
        mTextField.setText("done!")
    }
}.start()
```

此时可以使用 [`getCountDownTimer()`](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.os.extension/get-count-down-timer.html) 进行替代：

```kotlin
val mCDT = getCountDownTimer(30000, 1000, { it ->
    getBinding().content.text = "seconds remaining: " + it / 1000
}) {
    getBinding().content.text = "done!"
}.start()
```

对于只关心倒计时结束的开发者而言，使用 [`getCountDownTimer()`](https://api.ave.entropy2020.cn/VastTools/com.ave.vastgui.tools.os.extension/get-count-down-timer.html) 会让代码更加简洁：

```kotlin
val mCDT = getCountDownTimer(30000, 1000) {
    getBinding().content.text = "done!"
}.start()
```

