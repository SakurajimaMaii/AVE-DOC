# VastNetStateLayout

## 1.1.1(Latest)

- 新增 `NetState` 用来替代之前的 `CONTENT_STATE_SHOW_LOADING` 等常量
- 新增 `OnEmptyDataListener` ， `OnLoadingErrorListener` ， `OnLoadingListener` ， `OnNetErrorListener` 接口
- `VastNetStateMgr` 更名为 `NetStateMgr`
- `VastNetStateLayout` 更名为 `NetStateLayout`
- `showLoadingError` 支持传入请求返回值代码和信息
- `showNetError` 支持传入请求返回的异常
- 删除 `BaseNetStateLayout`
- 删除 `BaseNetStateMgr` 

## 0.0.4

- 新增 `BaseNetStateLayout`
- 新增 `BaseNetStateMgr` 

## 0.0.3

- 删除了 `SimpleNetErrorView` 和 `SimpleNetLoadingView`
- 删除了 `VastNetLoadingView` 和·`VastNetErrorView` 接口
- 新增 `VastNetStateMgr` 来管理界面监听事件和布局资源设定
- 新增 `CONTENT_STATE_SHOW_LOADING_ERROR` `CONTENT_STATE_SHOW_EMPTY_DATA` `CONTENT_STATE_SHOW_SUCCESS` 状态
- 针对四种网络状态设计了独立的接口

## 0.0.2

- `NetStateLayout` 更名为 `VastNetStateLayout`
- `NetState` 更名为 `VastNetState`
- `INetErrorView` 更名为 `VastNetErrorView`
- `INetLoadingView` 更名为 `VastNetLoadingView`
- `INetErrorView` 内的重试接口独立出来，新增 `VastRetry` 接口

## 0.0.1

- 用于设置自定义网络状态 ui 的布局