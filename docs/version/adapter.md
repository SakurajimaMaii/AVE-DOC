# adapter

## 1.2.0(Latest)🥳🥳🥳

- 更新：

    - 将 Adapter 基类都重命名为 BaseXXXAdapter 。 [**#199311a**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/199311a075eb04d43e31ef8b4988c8bdb66c0ec6)
    - 列表项点击事件应该仅关注数据部分，例如 `fun onItemClick(view: View, pos: Int, data: ItemWrapper<T>)` 更新为 `fun onItemClick(view: View, pos: Int, item: T?)` 。 [**#3575589**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/3575589dbd929c3251460d25b39ce6723cac8d64)
    - [BaseAdapter](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter/-base-adapter/index.html) 和 [BaseBindAdapter](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter/-base-bind-adapter/index.html) 新增以下方法：
  
        * `fun add(item: T, @LayoutRes layout: Int, position: Int, scope: ItemWrapper<T>.() -> Unit)` 
        * `fun add(items: List<T>, @LayoutRes layout: Int, position: Int, scope: ItemWrapper<T>.() -> Unit)` 
        * `fun add(item: ItemWrapper<T>, position: Int)` 
        * `fun add(items: List<ItemWrapper<T>>, position: Int)`
        * `update(item: T, @LayoutRes layout: Int, position: Int, scope: ItemWrapper<T>.() -> Unit)` 
        * `update(item: ItemWrapper<T>, position: Int)`
        * `fun removeAt(position: Int): T?`
        * `fun clear()`
        * `fun setEmptyView(@LayoutRes id: Int?, scope: ItemWrapper<T>.() -> Unit)`
  
    - [BaseListAdapter](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter/-base-list-adapter/index.html) 和 [BaseBindListAdapter](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter/-base-bind-list-adapter/index.html) 新增以下方法：
  
        * `fun submitList(items: List<T>, @LayoutRes id: Int? = null, commitCallback: Runnable? = null, scope: ItemWrapper<T>.() -> Unit)`
        * `submitListWithLoading()`
        * `fun setEmptyView(@LayoutRes id: Int?, scope: ItemWrapper<T>.() -> Unit)`
        * `fun setLoadingView(@LayoutRes id: Int?, scope: ItemWrapper<T>.() -> Unit)`

    - [BaseListAdapter](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter/-base-list-adapter/index.html) 和 [BaseBindListAdapter](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter/-base-bind-list-adapter/index.html) 重写了以下方法：

        * `fun submitList(list: List<ItemWrapper<T>>?)`
        * `fun submitList(list: List<ItemWrapper<T>>?, commitCallback: Runnable?)`

    - [BasePagingAdapter](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter/-base-paging-adapter/index.html) 和 [BaseBindPagingAdapter](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter/-base-bind-paging-adapter/index.html) 新增以下方法：

        * `suspend fun submitData(pagingData: PagingData<T>, @LayoutRes id: Int, scope: ItemWrapper<T>.() -> Unit)`
        * `fun submitData(lifecycle: Lifecycle, pagingData: PagingData<T>, @LayoutRes id: Int, scope: ItemWrapper<T>.() -> Unit)`

- 修复：

    - 修复 [ItemDiffUtil](https://api.ave.entropy2020.cn/adapter/com.ave.vastgui.adapter.base/-item-diff-util/index.html) 判断错误的问题。 [**#3ba979a**](https://github.com/SakurajimaMaii/Android-Vast-Extension/commit/3ba979a874bdafa56ecf387c2ef5772ede34446d)

## 1.1.1

- 更新：

    - 删除了原有的所有不合理逻辑。
