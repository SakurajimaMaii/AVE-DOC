# VastTools

## 0.5.6(Latest)

- 新增

    - `ExperimentalView` 注解
    - （实验性）暗夜模式切换组件 `MaskLayout` 和 `MaskView`
    - `RatingView` 新增评分进度监听接口
    - `DataStorePreference` 使用代理新实现
    - `SharedPreferences` 使用代理新实现
    - `PermissionUtils` 新增对未声明权限的提示

- 更新

    - `AlphabetSideBar` 适配 `SharedPreferences`
    - `RatingView` 更新 `Click` 方式的逻辑，从此版本开始，该方式代表选中的星星数量只会为整数
    - `LogSp` 适配 `SharedPreferences`
    - `LogStorage` 适配 `ResultCompat`
    - `FileMgr` 适配 `ResultCompat`
    - 适配不同版本定位和文件读写权限

- 修复

    - `SimpleToast` 显示错误的问题
    - `RatingView` 修复对 `padding` 的支持
    - `FileMgr` 修复 `moveFile` 移动文件后不删除源文件的问题
    - `MusicMgr` 修复 `fun getFileUriAboveApi30(file: File): Uri?` 添加时间键值错误的问题

- 删除

    - `FileMgr` 删除 `fun getPath(endWithSeparator: Boolean, vararg path: String): String` 方法
    - `FileProperty` 和 `FilePropertyMgr`

## 0.5.5

- 新增 

    - `ArcProgressView` 支持自定义终点圆形半径，支持隐藏文字，支持 xml 设置文字
    - `HorizontalTextProgressView` 支持 xml 设置文字，新增文字框颜色
    - `LineTextProgressView` 支持 xml 设置文字，新增文字框颜色
    - `WaveProgressView` 支持隐藏文字，直接设置圆形半径

- 更新

    - `ArcProgressView` 更新着色器设置方法
    - `HorizontalTextProgressView` 更新进度条和文字边距设置方法
    - `LineTextProgressView` 更新进度条和文字边距设置方法
    - `WaveProgressView` 更新图片的设置方法，外框线的距离以及外框线的宽度不再通过比率设置而是直接设置

- 修复

    - `ArcProgressView` 修复 `mShowEndpointCircle` 判断逻辑错误的问题
    - `WaveProgressView` 修复 stroke 在宽度设置为 0 仍有显示的问题

- 删除

    - `ProgressView` 删除以下方法

        * setMaximumProgress
        * setCurrentProgress
        * setText
        * setTextSize
        * setTextColor
        * setProgressBackgroundColor
        * setProgressColor

    - `WaveProgressView` 删除 hint 相关属性

## 0.5.4

- 新增

    - `AlphabetSideBar` 字母索引侧边导航栏
    - `viewSnapshot` 用于将视图保存为 `Bitmap`
    - `Avatar` 控件用于显示头像， `AvatarGroup` 布局用来显示头像组

- 更新

    - `ArcProgressView` 更新起始点和终点圆形颜色设置逻辑和属性设置方法
    - `HorizontalTextProgressView` 删除最小高度的占比
    - `LineTextProgressView` 允许设置进度条高度，更新字体外边距设置

- 修复

    - `ColorUtils` 修复获取带透明度颜色错误的问题
    - `HorizontalProgressView` 修复将图片设置为背景或者进度条时绘制错误的问题
    - `LineTextProgressView` 修复 [#53](https://github.com/SakurajimaMaii/Android-Vast-Extension/issues/53)
    - `HorizontalTextProgressView` 修复 [#52](https://github.com/SakurajimaMaii/Android-Vast-Extension/issues/52)

## 0.5.3

- 新增

    - 日志框架允许文件保存
    - 新增翻转动画
    - 新增徽标组件
    - 适用于 `GradientDrawable` 的拓展方法

- 更新

    - `CropViewLayout` 优化布局计算，父类更换为 `ConstraintLayout` ，将过时方法 `removeGlobalOnLayoutListener` 进行替换
    - `ColorUtils` 颜色转换增加透明度
    - `RatingView` 支持设置星星方向
    - `Vp2IndicatorView` 的 `setCurrentSelectedPosition` 将设定值 `position` 超出范围时抛出异常改为 `coerceIn` 来限制范围， `mBitmapSelected` 和 `mBitmapUnSelected` 由 `NotNUllVar` 进行委托
    - `MailBoxAssociateView` 更新默认支持邮箱
    - `ToastUtil` 更名为 `SimpleToast`
    - `ProgressView` 的 `setCurrentProgress` 将设定值 `currentProgress` 超出范围时抛出异常改为 `coerceIn` 来限制范围
    - `HorizontalProgressView` 重写了相关方法 ，优化了绘制流程
    - `HorizontalTextProgressView` 重写了相关方法，允许自定义进度条高度 `mProgressHeight` 和文本框外边距 `setTextMargin` ，`horizontal_text_progress_textbox_stroke_width` 属性更名为 `horizontal_text_progress_text_margin`
    - `LineTextProgressView` 的 `linetext_progress_textbox_stroke_width` 属性更名为 `linetext_progress_text_margin`
    - `DensityUtils` 针对 `px2sp` ， `sp2px` 和 `sp2dp` 对SDK 34进行适配
    - ViewModel 针对 `createViewModel` 更新默认获取实例方法对SDK 34进行适配

- 修复

    - 修复 `getWifiDBM` 在高版本和使用 vpn 时获取 wifi 强度错误的问题
 
- 过时

    - 废弃 `ResponseBuilder` 相关API

- 删除

    - `VastViewModel`
    - `VastService`
    - `ShapeAndStateDrawable` ，改为拓展方法
    - `RegexUtils` ，改为 `StrRegexKt` 拓展方法，删除 `isPwd` 方法和 `isPhoneNumber(string: String, otherCountryPattern: String?)` 方法

## 0.5.2

- 新增

    - `PwdRegex` 提供更好地密码验证
    - `UnitString` 提供了可供拓展的单位字符串
    - 重写了下载工具类，支持取消和断点续传
    - 重写了 `ViewBinding` 和 `ViewModel` 架构组件
    - 重写了日志架构组件，允许打印json，添加边框，删除了原来内容自定义
    - `WaveProgressView` 新增 `mUpdateInterval` 属性
    - 新增 `findByContext` 和 `findByResources` 以便为获取资源提供更好地兼容性方案
 
- 更新

    - `PermissionLauncher` 的构造函数添加 `internal` 修饰
    - `StrUnit` 由抽象类改为接口定义
    - `BmpUtils` 更新了部分方法
    - `ScreenSizeUtils` 更新 `getStatusBarHeight` 实现，获取屏幕尺寸，方向新增 `context` 参数

- 修复
  
    - `FileMgr` 修复 `getPath` 方法获取不到路径的问题
    - `Vp2IndicatorView` 修复 `setIndicatorItemCount` 方法不更新视图可见性的问题
    - `PermissionRegister` 修复因为 `Activity` 是 `FragmentActivity` 而导致 `ComponentActivity` 中不注册权限启动器的问题
    - `UnitString` 修复Ms单位错误描述为ms
    - 修改颜色的引用方式避免使用其他主题时无法获取到颜色而导致异常
    - `ScreenSizeUtils` 修复不同 API 版本 31 获取屏幕尺寸与屏幕方向有关，31 以下与屏幕方向无关而导致数据不一致的问题

- 过时

    - `RegexUtils` 废弃 `isPwd` 方法 

- 删除

    - 删除 `FileResult`
    - 删除 `convertClassToMap` 和 `convertClassToDefaultMap`
    - 删除 `Component` 提供的元祖功能
    - 删除 `ResUtils`

## 0.5.1

- 新增

    - `Request2` 简化网络请求
    - 适用于 `SharedPreferences` 的拓展方法
    - 适用于 `DataStore` 的拓展方法
    - `StrUtils` 新增拓展方法 `withUnit` ， `StrUnit` 新增 `getValue` 方法 
    - `AppendableStyleString` 用来构建多种样式文字
    - `FilePathScope` 用于构建文件路径

- 更新
   
    - `RequestBuilder` 提供默认实现，不再必须继承实现
    - `QRCodeUtil` 完善 `createQRCodeBitmap` 方法
    - `DateUtils` 完善 `datetimeFromString` 方法
    - `ResUtils` 完善默认值
    - `VastCropActivity` 默认裁剪框大小

- 修复

    - `AppUtils` 修复获取应用图标因为 `AdaptiveIconDrawable` 无法转换为 `BitmapDrawable` 的异常，完善默认值设置

- 过时

    - `StrUtils` 废弃 `getUnitStr` 方法
    - `FileMgr` 废弃 `fun getPath(endWithSeparator: Boolean, vararg path: String): String` 方法

- 删除

    - 删除 `SpDelegates`
    - 删除 `UriUtils`
    - 删除 `SpanStrUtils`

## 0.5.0

- 新增

    - 新增 `CropView` 和 `CropViewLayout` 自定义裁剪控件
    - `FileMgr` 新增 `fun getFileUriAboveApi24(file: File, authority: String): Uri` 和 `fun getFileUriOnApi23(file: File): Uri` 方法来获取文件 `Uri`
    - `BmpUtils` 新增 `scaleBitmap(bitmap: Bitmap, reqWidth: Int, reqHeight: Int): Bitmap?` 用来缩放 `bitmap` ，新增 `fun getBitmapWidthHeight(path: String): IntArray` 来获取 `bitmap` 的尺寸
    - 媒体文件新增 `fun getSharedFilesDir(): File` 和 `fun getExternalFilesDir(subDir: String?): File?` 方法获取媒体文件存储目录
    - `Vp2IndicatorView` 新增对 `Bitmap` 的支持

- 更新

    - `FileMgr` 修改 `getAssetsCacheFile` 文件的保存位置
    - `CropPhotoContract` 更新了返回值 `uri` 的获取方法

- 修复

    - `Vp2IndicatorView` 修复圆点绘制坐标计算问题，宽度为 `match_parent` 和 `wrap_content` 均可正确绘制

## 0.4.1

- 修复

    - `ResponseMutableLiveData` 修复对于 `setValue` 和 `postValue` 的错误重写

## 0.4.0

- 新增

    - `FileMgr` 新增文件复制和移动功能
    - `FileResult` 用于获取文件操作结果
    - `CropIntent` 新增支持自定义保存名称的功能

- 更新

    - `CropIntent` 修改 `setOutputFormat` 方法的可见性为 `protected`
    - `StrUtils` 将单位类变为单例类

- 修复

    - `CropPhotoContract` 修复关于在 Android 10 平台的兼容性问题

- 删除

    - `FileMgr` 删除对文本文件的写入
  
## 0.3.1

- 修复

    - `getSerializableExtra` 的错误导包导致对象无法转化

## 0.3.0

- 新增

    - `getRequestBuilder` 自动更新 `ResponseLiveData` 状态
    - `SpDelegates` 支持 `double` 类型
    - 新增 `ResponseMutableLiveData` ，原有的 `ResponseLiveData` 只能用来观察数据

- 更新
  
    - `SpDelegates` 修改 `getSharedPreferences` 可见性

## 0.2.0

- 新增
  
    - `BmpUtils` 新增 `fun getBitmapFromDrawable(@DrawableRes id: Int,context: Context): Bitmap` 方法
    - `StrUtils` 新增 `StrUnit` 便于继承和拓展
    - `SpanStrUtils` 新增 `mTextView` 变量来直接设置对应的视图，同时更新 `setUrl` 方法 
    - `FileMgr` 新增 `fun getAssetsCacheFile(fileName: String): String` 方法
    - 新增 `PermissionUtils` 
    - `ResUtils` 新增方法的 `context` 参数
    - 新增 `Vp2IndicatorView`
    - 新增 `MailBoxAssociateView`
    - 新增进度条类组件 `HorizontalProgressView` `HorizontalTextProgressView` `LineTextProgressView` `WaveProgressView`
    - 新增跑马灯组件 `MarqueeTextView`
    - 新增 `refreshWithInvalidate` `refreshWithPostInvalidate` `refreshWithRequestLayout`

- 更新
  
    - `DownloadCircleView` 更名为 `ArcProgressView`
    - `ArcProgressView` 更新对于开头结束圆点的设置
    - `LogUtils` 调换 `key` 和 `tag`
    - `RatingView` 更新默认图片

- 修复 

    - `FileMgr` 修复 `getPath` 对于 `endWithSeparator` 判定条件
    - `ToastUtils` 修复在子线程中被调用的问题
    - `DownloadUtils` 修复 `OKHttp` 的 `onFailure` 方法引用错误的参数类型 `okio.IOException`
    - `DownloadUtils` 移除 `ProgressManager` 的支持
    - `RequestImpl` 修复对于错误代码和错误信息的获取方式，具体参考 `ResponseStateListener.onFailed` 的描述

- 过时

    - `FocusedTextView` 不再建议使用

- 删除

    - 删除 `VastBroadcastReceiver`

## 0.1.0 

修复了诸多问题

## 0.0.8

- [ ] 删除了 `VastApp`
- [ ] 删除了 `VastTools` 内MMKV的支持 [#issue 39](https://github.com/SakurajimaMaii/VastUtils/issues/39) 
- [x] 新增 `DownloadUtils` 工具类，提供下载支持
- [x] 新增 `MapUtils` 工具类，用以判断GPS状态
- [x] 新增 `BaseFragmentAdapter`，用来快速构建适用于 [ViewPager2](https://developer.android.com/jetpack/androidx/releases/viewpager2) 的适配器
- [x] 新增 `FocusedTextView`，用于构建跑马灯
- [x] 新增 `DownloadCircleView` 下载进度条控件
- [x] `BaseActivity` 新增 `mContext` 属性
- [x] 修复 `VastSkinResources` 在获取资源时会因为给定的资源id找不到而导致NotFoundException，使得应用闪退的问题 [#issue 38](https://github.com/SakurajimaMaii/VastUtils/issues/38) 
- [x] 修复 `VastBaseFragment` 在使用ViewModel通信时会出现问题 [#issue 42](https://github.com/SakurajimaMaii/VastUtils/issues/42)


## 0.0.7

- [x] 修复 `LogUtils` 的 syncIsDeBug 方法被错误的加上了 internal 关键字的问题  [#issue 37](https://github.com/SakurajimaMaii/VastUtils/issues/37) 

## 0.0.6

- [ ] 删除了 `CheckPermission` 注解
- [ ] 删除了 `UnderTest` 注解
- [ ] 删除了 `ColorUtils` 颜色获取方法
- [x] 新增基于 [AppCompatActivity](https://developer.android.com/reference/androidx/appcompat/app/AppCompatActivity) 封装的 Activity 基类，目前有 `VastVbActivity` `VastVbVmActivity` `VastVmActivity`
- [x] 新增基于 [Fragment](https://developer.android.com/reference/androidx/fragment/app/Fragment.html) 封装的 Fragment 基类，目前有 `VastVbFragment` `VastVbVmFragment` `VastVmFragment`
- [x] 新增基于 [Factroy2](https://developer.android.com/reference/android/view/LayoutInflater.Factory2) 实现的 `VastSkin` 插件
- [x] 新增 `IDCardUtils` 工具类，提国居民身份证号码本地校验
- [x] 新增 `RegexUtils` 工具类，提供了一些字符串格式正则检查
- [x] 新增 `NetStateUtils` 工具类，提供网络检查
- [x] `DensityUtils` 新增 `.px` `.pt` `.mm` `.inches` 拓展方法
- [x] `IntentUtils` 新增 [RequiresPermission](https://developer.android.com/studio/write/annotations?hl=zh-cn#permissions) 来检查权限
- [x] `IntentUtils` 新增 `openWirelessSettings` 方法
- [x] 优化 `Response` 设计，将 `data` 部分改进为泛型
- [x] 修复 `LogUtils` 日志工具类由于使用 `BuildConfig.DEBUG` 而导致的不打印日志的问题 [#issue 33](https://github.com/SakurajimaMaii/VastUtils/issues/33)
- [x] 修复 `ScreenSizeUtils` 横屏模式下获取到的宽度出错问题 [#issue 34](https://github.com/SakurajimaMaii/VastUtils/issues/34) 

## 0.0.5

- [ ] 移除了 `CameraUtils` 工具类
- [ ] 移除了 `UrlValidator` 网络Url验证器
- [ ] `ScreenSizeUtils` 现在不再支持全面屏判断，只能获取屏幕的长宽
- [ ] 删除了 `AspectRatioDevice` ，不再支持定义更多的设备类型以及其对应的屏幕长宽比来判断全面屏
- [ ] `MsgWindowUtils` 不再支持弹出 `Dialog`
- [x] 新增 `ColorUtils` 工具类
- [x] 新增 `ShapeAndStateUtils` 工具类
- [x] 新增 `User` 和 `Response` 两个Bean
- [x] 优化了 `DateUtils` 工具类，修复了部分逻辑
- [x] `IntentUtils` 添加了 `resolveActivity` 判断，针对API 30以上的情况设定了提示信息
- [x] 修复日志打印logPrint函数存在的逻辑问题，删除了需要添加Class的环节，优化日志打印对于长度判断的设定，LogContent接口移动至 `LogUtils.kt` 内
- [x] `MsgWindowUtils` 更名为 `ToastUtils`

## 0.0.4

- [ ] `NoMatchAspectRatio` 异常
- [ ] `BuildVersionException` 异常
- [ ] 附带的140种颜色
- [x] 新增 `MergeBitmapUtils` BitMap合并工具类
- [x] 新增 `SystemUtils` 工具类
- [x] `DateFormat` 添加了常用的时间格式以及GMT时区
- [x] `DateFormatString` `GmtFormatString` `YearFormatString` 注解用来判断DateUtils内的参数类型
- [x] 完善 `DateUtils` 方法和注释
- [x] 全面屏判断由 `isAllScreenDevice` 根据 **Build.VERSION.SDK_INT** 选择对应的API，`isAllScreenDeviceApi31` ， `isAllScreenDeviceApi30` ，`isAllScreenDeviceApi30Down` 不可从外部调用
- [x] 屏幕高度获取由 `getMobileScreenHeight` 根据 **Build.VERSION.SDK_INT** 选择对应的API， `getMobileScreenHeightApi31` ，`getMobileScreenHeightApi30` ， `getMobileScreenHeightApi30Down` 不可从外部调用
- [x] 修复 `ScreenSizeUtils` 屏幕高度获取存在问题

## 0.0.3

- [x] 修复了日志打印不全解决的问题
- [x] 修复日志打印堆栈信息有时候存在不匹配问题
- [x] 支持定义更多的设备类型以及其对应的屏幕长宽比来判断全面屏

## 0.0.2

- [ ] 删除了Adapter部分

## 0.0.1

- [x] 将原本的代码由 `jitpack` 迁移至 `mavencentral` ，**该版本还包含Adapter部分**