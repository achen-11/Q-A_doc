# JavaScript
## 1. 判断手机系统
```js
_getEnv() {
    const u = navigator.userAgent.toLocaleLowerCase();

    // 微信环境
    if (u.indexOf('micromessenger') !== -1) {
    this.plateForm = 'micromessenger';
    this.version = u.match(/micromessenger\/(\d+\.*\d+)/i);
    return;
    }
    // IOS
    if (u.match(/OS\s*(\d+)/i)) {
    this.plateForm = 'ios';
    this.version = u.match(/OS\s*(\d+)/i)[1];
    return;
    }
    // Android
    if (u.match(/Android\s*(\d+)/i)) {
    this.plateForm = 'android';
    this.version = u.match(/Android\s*(\d+)/i)[1];
    return;
    }
    // 其他环境
    this.plateForm = 'anonymous';
}
```

# js生成m x n的二维数组

```js
new Array(m).fill(0).map(() => new Array(n).fill(0))
```