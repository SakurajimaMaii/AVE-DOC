# Common intent

`IntentUtils` provides some useful [Intent](https://developer.android.com/guide/components/intents-common) . 

!!! warning 
    
    If the SDK of device is above Android 11(API>=30)，you should add following content in `AndroidManifest.xml` ：
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

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/java/com/ave/vastgui/app/activity/IntentActivity.kt){ .md-button }
