# 常见 Intent

`IntentUtils` 为你提供了一些常见 [Intent](https://developer.android.com/guide/components/intents-common?hl=zh-cn) 。

!!! warning 
    
    如果你的设备是Android 11(API>=30)，你应该在清单中做出如下声明，否则可能会找不到对应的Activity。例如：
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

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/activity/IntentActivity.kt){ .md-button }
