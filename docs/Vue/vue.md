# vue
# Vue自定义事件-点击空白处触发事件
```js
Vue.directive('clickoutside', {
    bind (el, binding) {
        function documentHandler (e) {
            if (el.contains(e.target)) {
                return false;
            }
            if (binding.expression) {
                binding.value(e);
            }
        }
        el.__vueClickOutside__ = documentHandler;
        document.addEventListener('click', documentHandler);
    },
    unbind (el) {
        document.removeEventListener('click', el.__vueClickOutside__);
        delete el.__vueClickOutside__;
    }
});
```

# Vue.$set


# Vue动态设置页面title
解决方案:<br>
通过路由守卫获取router.meta的title属性, 动态设置路由
```js
// 路由配置
const route = [
    {
        path: '/test',
        meta: {
        }

    }
]

// 路由守卫
this.router.beforeEach((to, from, next) => {
    window.document.title = to.meta.title == undefined ? '默认标题' : to.meta.title
})

```