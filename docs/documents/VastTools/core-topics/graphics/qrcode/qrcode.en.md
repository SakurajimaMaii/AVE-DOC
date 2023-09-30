# QRCode

`QRCode` is based on [zxing](https://github.com/zxing/zxing), and you can convert the specified content into a QR code through the `createQRCodeBitmap` method.

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
  <figcaption>QRCode</figcaption>
</figure>

[Sample Code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app-compose/src/main/java/com/ave/vastgui/appcompose/example/graphics/QRCode.kt){ .md-button }

