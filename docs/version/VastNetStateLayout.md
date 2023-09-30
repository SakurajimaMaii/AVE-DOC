# VastNetStateLayout

## 0.0.4(Latest)

- [x] 新增 `BaseNetStateLayout`
- [x] 新增 `BaseNetStateMgr` 

## 0.0.3

- [ ] 删除了 `SimpleNetErrorView` 和 `SimpleNetLoadingView`
- [ ] 删除了 `VastNetLoadingView` 和·`VastNetErrorView` 接口
- [x] 新增 `VastNetStateMgr` 来管理界面监听事件和布局资源设定
- [x] 新增 `CONTENT_STATE_SHOW_LOADING_ERROR` `CONTENT_STATE_SHOW_EMPTY_DATA` `CONTENT_STATE_SHOW_SUCCESS` 状态
- [x] 针对四种网络状态设计了独立的接口

## 0.0.2

- [x] `NetStateLayout` 更名为 `VastNetStateLayout`
- [x] `NetState` 更名为 `VastNetState`
- [x] `INetErrorView` 更名为 `VastNetErrorView`
- [x] `INetLoadingView` 更名为 `VastNetLoadingView`
- [x] `INetErrorView` 内的重试接口独立出来，新增 `VastRetry` 接口

## 0.0.1

- [x] 用于设置自定义网络状态 ui 的布局