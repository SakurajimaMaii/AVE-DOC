# MailBoxAssociateView

<figure markdown>
  ![MailBoxAssociateView](../img/mail-box-associate-view.gif){ width="250" }
  <figcaption>MailBoxAssociateView</figcaption>
</figure>

## Quick start

[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

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

[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053)

```java
qq.com
163.com
126.com
gmail.com
139.com
hotmail.com
sina.com
me.com
```

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/TextViewActivity.kt){ .md-button }
