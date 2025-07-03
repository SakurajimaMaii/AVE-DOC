# MailBoxAssociateView

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

<figure markdown>
  ![MailBoxAssociateView](../img/mail-box-associate-view.gif){ width="250" }
  <figcaption>MailBoxAssociateView</figcaption>
</figure>

## Quick start

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

```xml
<com.google.android.material.textfield.TextInputLayout
    android:id="@+id/text_input"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="20dp"
    app:layout_constraintTop_toTopOf="parent">
    <com.ave.vastgui.tools.view.mailboxassociateview.MailBoxAssociateView
        android:id="@+id/mailBoxAssociateView"
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:padding="10dp"
        android:hint="请输入邮箱"/>
</com.google.android.material.textfield.TextInputLayout>
```

## Default support mail address

> Add:[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020) &emsp; Update:[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

| Region        | Email Suffix    | Description                                                  |
| ------------- | --------------- | ------------------------------------------------------------ |
| China         | @qq.com         | Tencent QQ email, one of the most popular in China           |
| China         | @163.com        | NetEase 163 email, widely used                               |
| China         | @126.com        | NetEase 126 email, common for personal use                   |
| China         | @sina.com       | Sina email, popular in earlier years                         |
| China         | @sohu.com       | Sohu email, used by early adopters                           |
| China         | @aliyun.com     | Alibaba Cloud email, suitable for businesses and individuals |
| China         | @yeah.net       | Another NetEase email service                                |
| International | @gmail.com      | Google email, globally popular                               |
| International | @outlook.com    | Microsoft email, widely used for personal and business       |
| International | @yahoo.com      | Yahoo email, popular in earlier years                        |
| International | @hotmail.com    | Microsoft’s early email service                              |
| International | @icloud.com     | Apple email, common among Apple device users                 |
| International | @protonmail.com | ProtonMail, focused on privacy protection                    |
| International | @aol.com        | AOL email, used by early internet adopters                   |

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/TextViewActivity.kt){ .md-button }
