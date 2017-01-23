## 效果图
![images](http://ok7n02kz6.bkt.clouddn.com/FjgC9YLSpadne_Ou04-eQ9gfSJ_-.gif)
# 知识点：
## 1. NodeList 和 Array 的区别
可以打开 proto 查看它的方法，其中有 forEach()、item()、keys() 等。而 Array 的 prototype 中有 map()、pop() 等数组才有的方法。

## 2.HTML5 中的自定义数据属性 dataset
HTML5 中可以为元素添加非标准的自定义属性，只需要加上 data- 前缀，可以随便添加和命名。添加之后，可以通过元素的 dataset 属性来访问这些值，dataset 的值是 DOMStringMap 的一个实例化对象，其中包含之前所设定的自定义属性的“名-值”对。

## 3.CSS variable
这是一个 CSS3 的新特性，IE 和 Edge 目前都还不支持。命名写法是 --变量名，在引用这个变量时写法是 var(--变量名)。

## 4:root 伪类
这个伪元素匹配的是文档的根元素，也就是 <html> 标签。

```html
:root {
   --base: #ffc600;
   --blur: 10px;
   --padding: 10px;
}
```

运用时
```
img {
       padding: var(--spacing);
       background: var(--base);
       filter: blur(var(--blur));
   }
```

# 技能
## 1.如何处理参数值（一个有 px 、另一个没有）
运用 dataset 储存后缀，有 px 后缀的标签中设置 `<input data-sizing="px">`：
```HTML
 <input type="range" name="blur" min="0" max="25" value="10" data-sizing="px">
 <input type="color" name="base" value="#8aa8af">
```

## 2.JS 中通过 dataset.sizing 来获取后缀值：
`const suffix = this.dataset.sizing || ''`
此时 suffix 获取到的值，针对颜色为空，而针对长度类的则为 'px'。

## 3.用 JavaScript 改变 CSS 属性值
在 JavaScript 中 document.documentElement 即代表文档根元素。所以要改变全局的 CSS 变量，可以这样写：
```
document.documentElement.style.setProperty('--base', '#fff');
```


PS:新发现的一个网址
[Unsplash Source](https://dingdingbai.github.io/CSS-variables/.)
upsplash gallery的API,可以随机的展示出unsplash gallery里的图片