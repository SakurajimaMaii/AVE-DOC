# 常见 Intent

`IntentUtils` 为你提供了一些常见 [Intent](https://developer.android.com/guide/components/intents-common?hl=zh-cn) 。

!!! warning 
    
    如果您的应用以 Android 11（API 级别 30）或更高版本为目标平台，在默认情况下，系统会[自动让部分应用对您的应用可见](https://developer.android.com/training/basics/intents/package-visibility?hl=zh-cn#automatic)，但会隐藏其他应用。通过让部分应用在默认情况下不可见，系统可以了解应向您的应用显示哪些其他应用，这样有助于鼓励最小权限原则。

    如果你想打开系统电话，需要在清单文件中声明以下内容：

    ```xml
    <queries>
        <intent>
            <action android:name="android.intent.action.DIAL"/>
        </intent>
    </queries>
    ```

## 快速开始

![IntentUtils](../img/intent_utils.gif){ align=right width="250" } 

=== "Kotlin"

    ```kotlin
    mBinding.callBtn.setOnClickListener {
        dialPhoneNumber(this, "12345678910")
    }
    ```

=== "Java"

    ```java
    phoneCall.setOnClickListener(view -> 
        dialPhoneNumber(this, myUserProfile.getPhone())
    );
    ```

如上代码所演示的，通过调用 `dialPhoneNumber` 即可拨打电话。目前 `IntentUtils` 提供了以下快捷方式：

|      方法       |      说明      |
| :-------------: | :------------: |
| dialPhoneNumber |    拨打电话    |
|    searchWeb    |  搜索指定内容  |
|   openWebPage   | 打开指定的网页 |
| sendMmsMessage  |    发送短信    |
|    openEmail    |    发送邮件    |
|   createAlarm   |    创建闹钟    |
|   wifiSetting   | 打开 WIFI 设置 |

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/IntentActivity.kt){ .md-button }
