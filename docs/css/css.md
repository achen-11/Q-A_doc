# css
## 1.颜色值设为透明
```css
color: transparent
```
## 2.设置渐变色背景
详见：[MDN-CSS渐变](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Images/Using_CSS_gradients)
```css
/* 从上往下线性渐变 */
background: linear-gradient(color1 , color2, colorN);
```

## 3.position居中解决方案
```css
/* 容器宽高未知 */
.container {
    position: absolute;
    top: 50%;
    left: 50%;
    transform:translate(-50%,-50%);
}
```
还有一种情况, 容器内文字过多可能会导致自动换行,不能达到我们想要的效果(如图)

![](../img/css-3.png)

可以通过white-space属性强制不换行
```css
.container {
    white-space: nowrap;
}

```
![](../img/css-3-2.png)