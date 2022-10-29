# uView
## 1.使用Hbuild引入uView报错
使用`uniModules`引入到项目时还需要做以下操作, 否则会报错
1. 引入uView `main.js`
```js
// main.js
import uView from '@/uni_modules/uview-ui'
Vue.use(uView)
```
2. 添加全局样式 `uni.scss`
```css
/* uni.scss 文件 引入uView的全局SCSS主题文件 */
@import 'uview-ui/theme.scss';
```
3. 引入uView基础样式 `App.vue`
```html
<!-- App.vue -->
<style lang="scss">
    /* 注意要写在第一行，同时给style标签加入lang="scss"属性 */
    @import "uview-ui/index.scss";
</style>
```

## 2.使用npm引入uView
- npm 安装 uview
```bash
npm install uview-ui
```
- 引入步骤除了上述操作, 还需要配置easycom组件模式
```json
{
    "easycom": {
        "^u-(.*)": "@/uni_modules/uview-ui/components/u-$1/u-$1.vue"
    },
    // 文件原有内容
    "pages": {
        // ...
    }
}
```
