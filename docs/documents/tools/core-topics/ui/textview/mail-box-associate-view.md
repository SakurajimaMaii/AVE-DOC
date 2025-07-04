# 邮箱补足

> 添加：[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

<figure markdown>
  ![MailBoxAssociateView](../img/mail-box-associate-view.gif){ width="250" }
  <figcaption>MailBoxAssociateView</figcaption>
</figure>

## 快速使用

> 添加：[:octicons-tag-24: Version 0.2.0](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#020)

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

## 默认支持的邮箱

> 添加：[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053) &emsp; 更新：[:octicons-clock-24: Version 1.5.2](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#152)

| 地区     | 邮箱后缀        | 描述                             |
| -------- | --------------- | -------------------------------- |
| 中国境内 | @qq.com         | 腾讯QQ邮箱，国内最常用的邮箱之一 |
| 中国境内 | @163.com        | 网易163邮箱，广泛使用            |
| 中国境内 | @126.com        | 网易126邮箱，常见于个人用户      |
| 中国境内 | @sina.com       | 新浪邮箱，较早的邮箱服务         |
| 中国境内 | @sohu.com       | 搜狐邮箱，早期用户较多           |
| 中国境内 | @aliyun.com     | 阿里云邮箱，适合企业和个人       |
| 中国境内 | @yeah.net       | 网易旗下另一邮箱服务             |
| 国外     | @gmail.com      | 谷歌邮箱，全球最流行             |
| 国外     | @outlook.com    | 微软邮箱，广泛用于个人和企业     |
| 国外     | @yahoo.com      | 雅虎邮箱，早期流行               |
| 国外     | @hotmail.com    | 微软早期邮箱服务                 |
| 国外     | @icloud.com     | 苹果邮箱，常见于苹果设备用户     |
| 国外     | @protonmail.com | ProtonMail，注重隐私保护         |
| 国外     | @aol.com        | 美国在线邮箱，早期用户较多       |

## 示例代码

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/view/TextViewActivity.kt){ .md-button }
