# 概览

[![version](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/VastNetStateLayout)](https://img.shields.io/maven-central/v/io.github.sakurajimamaii/VastNetStateLayout)
[![Min SDK Version](https://img.shields.io/badge/min%20sdk%20version-23-yellowgreen)](https://img.shields.io/badge/min%20sdk%20version-23-yellowgreen)
[![JDK Version](https://img.shields.io/badge/jdk%20version-17-2300b894?style=flat)](https://img.shields.io/badge/jdk%20version-17-2300b894)
[![GitHub license](https://img.shields.io/badge/license-Apache%20License%202.0-blue.svg?style=flat)](https://www.apache.org/licenses/LICENSE-2.0)

`VastNetStateLayout` 继承自 [FrameLayout](https://developer.android.com/reference/android/widget/FrameLayout) 。你可以自定义下列状态页面: loading ，error ，ok ，empty data 。

## 特性

- 👍 支持自定义四种状态页面 `loading 加载页面` `empty data 空数据页面` `net error 网络错误页面` `retry 重试界面`
- 👍 支持自定义重试或者网络错误事件
- 👍 使用 `VastNetStateMgr` 进行界面管理
- 👍 设置有默认界面，添加即用

<div align="center">
<img src="./img/empty_data.png" width=30%/>
<img src="./img/loading_error.png" width=30%/>
<img src="./img/loading.png" width=30%/>
<img src="./img/network_error.png" width=30%/>
</div>
