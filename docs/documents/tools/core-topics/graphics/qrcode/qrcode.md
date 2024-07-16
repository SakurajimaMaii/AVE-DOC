# 二维码

`QRCode` 基于 [zxing](https://github.com/zxing/zxing) 实现，通过 `createQRCodeBitmap` 方法你可以将指定内容转换为二维码。

```kotlin
@Composable
fun QRCode() {
    Box(
        contentAlignment = Alignment.Center,
        modifier = Modifier.fillMaxSize()
    ) {
        val qrCode = QRCode.createQRCodeBitmap("Hello", 800, 800)
        Image(bitmap = qrCode.asImageBitmap(), contentDescription = null)
    }
}
```

<figure markdown>
  ![QRCodeUtil](../img/qrcode.png){ width="200" }
  <figcaption>二维码</figcaption>
</figure>

[查看示例代码](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/kotlin/com/ave/vastgui/appcompose/example/graphics/QRCode.kt){ .md-button }
