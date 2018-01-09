# wabQR

实现指定tag（svg | table | canvas）渲染生成二维码，支持带有中间logo的二维码，兼容大部分浏览器

### 动机坦白

其实生成二维码的锅完全可以扔给后端童鞋完成，但是从业务优化来说，前端渲染可以减小带宽，缓解服务器压力，最重要的是我闲的~~:sweat_smile:

代码的核心其实是[qrcode.js](http://jeromeetienne.github.com/jquery-qrcode/),很强大很给力的插件:thumbsup:，
但是为了更好的无缝对贴业务需求，在源代码的基础上扩展了部分功能，也是方便以后闭眼使用

### 函数功能

- [√] 支持中文字符
- [√] 支持指定tag生成二维码
- [√] 支持中间logo的展示
- [√] 兼容IE6~10, Chrome, Firefox, Safari, Opera, Mobile Safari, Android, Windows Mobile, ETC.

### 使用方法

普通调用，实例化wabQR对象

```html
<div id="qr"></div>
<script type="text/javascript">
new wabQR(document.getElementById("qr"), "http://jindo.dev.naver.com/collie");
</script>
```

还可以设置option调用

```html
<div id="qr"></div>
<script type="text/javascript">
new wabQR(document.getElementById("qr"), {
  text: "http://jindo.dev.naver.com/collie",
  width: 128,
  height: 128,
  colorDark : "#000000",
  colorLight : "#ffffff",
  correctLevel : wabQR.CorrectLevel.H,
  render: 'svg',  // 不设置的话默认根据浏览器的兼容情况选择最优
  logoSrc: 'logo.jpg',
  logoRate: 0.4
});
</script>
```
还可以调用方法
```js
qrcode.clear(); // clear the code.
qrcode.makeCode("http://naver.com"); // make another code.
```

### 效果展示
![截图展示](exmple.png)
