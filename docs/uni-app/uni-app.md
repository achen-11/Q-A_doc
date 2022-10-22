#
# 1. uni-app的跳转问题
uni-app带有多种跳转方式`uni.navigateTo`、`uni.redirectTo`、`uni.reLaunch`、`uni.switchTab`

> 详见: https://uniapp.dcloud.net.cn/api/router.html#navigateto
```js
// eg. 跳转页面
uni.navigateTo({url: 'url'})
```
## 常用参数:(摘自官网)

|参数|类型|必填|说明|
|---|---|---|---|
|url|String|是|要跳转的页面地址|
|success|Function|否|调用成功的回调函数|
|fail|Function|否|调用失败的回调函数|
|complete|Function|否|调用结束后的回调函数|

## 跳转方式的区别
> 注意: 跳转到 tabBar 页面只能使用 switchTab 跳转

|跳转方法| 区别|
|---|---|
|uni.navigateTo|**保留**当前页面，跳转到应用内的某个页面，使用`uni.navigateBack`可以返回到原页面。|
|uni.redirectTo|**关闭**当前页面，跳转到应用内的某个页面|
|uni.reLaunch|**关闭所有**页面，打开到应用内的某个页面。|
|uni.switchTab|跳转到 tabBar 页面，并**关闭其他所有非 tabBar 页面**。

> 更多详情可前往官网查看: https://uniapp.dcloud.net.cn/api/router.html#navigateto




