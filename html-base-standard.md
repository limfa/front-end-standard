# HTML编码规范

## 缩进

统一**4个空格**缩进

#### 影响

（无）

#### 例子

（无）

#### 重要性

推荐


## 排版

标签中有多个子标签，则子标签缩减，父标签开始和闭合在上下两边；如果一标签包含行内标签，则最好不换行

#### 影响

换行的`inline/inline-block`标签之间（可能）会存在空隙

#### 例子

```html
<!-- 不推荐 -->
<div><p>xxxxxxxxxxxxxxxxxxx</p>
    <p>xxxxxxxxxxxxxxxxxxx</p></div>
<!-- 推荐 -->
<div>
    <p>xxxxxxxxxxxxxxxxxxx</p>
    <p>xxxxxxxxxxxxxxxxxxx</p>
</div>
```
```html
<!-- 推荐 -->
<div>
    <a href="">1</a>
    <a href="">2</a>
    <a href="">3</a>
</div>
<!-- 推荐 -->
<div><a href="">1</a><a href="">2</a><a href="">3</a></div>
<!-- 推荐 -->
<div>
    <a href="">1</a><!--
    --><a href="">2</a><!--
    --><a href="">3</a>
</div>
```

#### 重要性

推荐


## 大小写

和内容无关的文本一律**小写**，比如标签名、属性等。

#### 影响

（无）

#### 例子

    <!-- 不推荐 -->
    <DIV CLASS="classname"></DIV>
    <!-- 推荐 -->
    <div class="classname"></div>

#### 重要性

推荐


## 文档声明

统一使用`<!DOCTYPE html>`，文档声明必须放在页面**第一行**，在它之前**不能有字符**

#### 影响

不声明或使用其它文档声明会造成意想不到的结果

#### 例子

（无）

#### 重要性

必须


## 引号

属性名一律使用**双引号**

#### 影响

（无）

#### 例子

```html
<!-- 不推荐 -->
<a href='javascript:' data-value='xxx'></a>
<!-- 推荐 -->
<a href="javascript:" data-value="xxx"></a>
```

#### 重要性

推荐


## 自定义属性

自定义属性以`data-`开头

#### 影响

区别内置属性；可通过HTML5api来获取

#### 例子

```html
<!-- 不推荐 -->
<div role="button"></div>
<!-- 推荐 -->
<div data-role="button"></div>
```

#### 重要性

必须


## 页面编码

采用*utf-8*编码，如`<meta charset="utf-8" />`

#### 影响

不同的编码易造成乱码

#### 例子

（无）

#### 重要性

必须


## JAVASCRIPT分离

1. 避免在HTML文件中添加事件处理函数
2. 避免在HTML文件中出现内联JavaScript代码

#### 影响

不利于维护

#### 例子

```html
<!-- 不推荐 -->
<!DOCTYPE html>
<html>
<!-- ... -->
<body>
    <!-- ... -->
    <button onclick="doSomething()">来点我呀</button>
    <script>
         // doSomething();
    </script>
</body>
</html>
```
```html
<!-- 推荐 -->
<!DOCTYPE html>
<html>
<!-- ... -->
<body>
    <!-- ... -->
    <button id="actionBtn">来点我呀</button>
    <script src="script.js"></script>
</body>
</html>
```
script.js
```js
document.getElementById('actionBtn').onclick = function(){
    // todo
};
// doSomething();
```

#### 重要性

推荐


## 协议

对资源的引用，需要指定具体域名时，`http`或`https`协议的，可以不需要具体指定

#### 影响

http与https之间的转换便捷

#### 例子

```html
<!-- 不推荐 -->
<script src="http://cdn.com/script.js"></script>
<!-- 推荐 -->
<script src="//cdn.com/script.js"></script>
```

#### 重要性

推荐