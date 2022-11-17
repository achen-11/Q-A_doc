#
# 1.uni-app的跳转问题
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

# 2.uni-app启动微信小程序显示`open IDE x`问题

```bash
一般是appid的问题, 可能是appid不对或者登录的用户没有这个appid的开发权限
```

# 3.uni-app项目常用`.gitignore`配置
```
node_modules/
.project
unpackage/
.DS_Store
```

# 4.`swiper`在安卓不显示问题
场景:<br>
>    动态生成`swiper-item`标签内的内容时, 安卓系统标签内内容会不显示,需要滑动之后显示

解决方案:<br>
>    在`swiper-item`内添加一个占位标签即可解决

# 5.小程序`padding-right\bottom`不生效
解决方案:<br>
>    给外容器加上`box-sizing: border-box;`即可解决

# 6.uni-app获取路由栈/前几级路由地址
解决方案:<br>
`getCurrentPages()` 函数用于获取当前页面栈的实例，以数组形式按栈的顺序给出，第一个元素为首页，最后一个元素为当前页面。<br>
注意： `getCurrentPages()`仅用于展示页面栈的情况，请勿修改页面栈，以免造成页面状态错误。
```js
const urlArr = uni.getCurrentPages() // 获取页面栈
console.log(urlArr[urlArr.length - 1].route) // 获取当前页的url
```

# 7.uni-app获取元素位置