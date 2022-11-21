# vue
# 1.Vue自定义事件-点击空白处触发事件
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

# 2.Vue.$set


# 3.Vue动态设置页面title
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

# 4.Vue发布订阅
场景:
> 

# 5.Vue解决滑动穿透
移动端:

    
# 6.`v-for`在H5和小程序的差异
`v-for Number`在H5和小程序的表现有差异:
- 小程序是从**0**开始
- H5是从**1**开始

# 7.实现`ctrl+s`快捷键保存和自动保存
```html
<template>
  <button @click="save('button')">保存</button>
</template>
 
<script>
 
export default {
  mounted() {
    // 监听keydown事件
    document.addEventListener('keydown', this.saveContent)
    // 定义计时器
    this.timer = setInterval(() => {
      this.save('timer')
    }, 10 * 1000)
  },
 
  beforeDestroy() {
    // 移除监听事件
    document.removeEventListener('keydown', this.saveContent)
    // 清楚计时器
    clearInterval(this.timer)
  },
 
  methods: {
    // 保存
    save(type) {
      console.log(`content saved by ${type}`)
    },
    // 监听的回调
    saveContent(e) {
      var key = window.event.keyCode ? window.event.keyCode : window.event.which
      // 如果是ctrl+s
      if (key === 83 && e.ctrlKey) {
        this.save('hot key')
        e.preventDefault() // 阻止默认事件
      }
    }
  }
}
</script>
```