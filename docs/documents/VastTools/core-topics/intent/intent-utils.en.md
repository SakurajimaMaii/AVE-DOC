# Common intent

`IntentUtils` provides some useful [Intent](https://developer.android.com/guide/components/intents-common) . 

!!! warning 
    
    When an app targets Android 11 (API level 30) or higher and queries for information about the other apps that are installed on a device, the system filters this information by default. This filtering behavior means that your app can’t detect all the apps installed on a device, which helps minimize the potentially sensitive information that your app can access but doesn't need to fulfill its use cases.

    For example, if you want to use the default phone app, declare the following in `AndroidManifest.xml` .

    ```xml
    <queries>
        <intent>
            <action android:name="android.intent.action.DIAL"/>
        </intent>
    </queries>
    ```

## Quick start

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

As demonstrated in the code above, a call can be made by using `dialPhoneNumber`. Currently `IntentUtils` provides the following intents:

|    function     |           detail            |
| :-------------: | :-------------------------: |
| dialPhoneNumber |         Dial number         |
|    searchWeb    |   Search specific content   |
|   openWebPage   | Open the specified web page |
| sendMmsMessage  |        Send messages        |
|    openEmail    |         Send email          |
|   createAlarm   |       Create a alarm        |
|   wifiSetting   |      Open WIFI setting      |

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/IntentActivity.kt){ .md-button }
