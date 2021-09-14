# HTML常用标签
## 1.a标签的用法
a标签的作用为可以跳转外部的链接，内部的锚点或者是发送邮件或者拨打电话。

它的属性主要有href、target、download和rel，以下依次进行介绍：

1. href(hyper reference),意为超链接，它的取值可以是网址、路径、伪协议或者id。
   
   ①网址的取值有三种，分别为"https://google.com";"http://google.com";"//google.com"，其中最后一种不加协议的写法会自动选择跳转http或https。
   
   ②路径的取值有"/a/b/c.html";"a/b/c.html",这两种写法效果是一致的，因为当开启了http服务时，此时的根目录指的并不是硬盘的根目录，而是默认为开启http服务的目录。同样"index.html"和"./index.html"这两种写法是一样的。
   
   ③伪协议的取值有"javaScript:代码;",最常用的是javascript:;如可表示点击后什么都不做，其中:和;不能省略。"mailto: + 邮箱地址"，"tel: + 手机号"代表发邮件或打电话。
   
   ④id 当给页面中某个标签设置了id时，可以通过设置href为#+id的方式，直接跳转到某个id的标签处。

2. target 默认为_blank，意为在新窗口打开页面；_self，在当前窗口打开页面；_top，在顶级窗口打开新页面，举例：若index.html包含iframe1.html，iframe1.html包含iframe2.html，若在iframe2中点击某个target为_top的超链接，则会在index.html中打开这个页面；_parent，在上一层级的窗口中打开，同上个例子，此时会在iframe1.html中打开页面。我们也可以将target设置为xxx，当点击链接时，若有叫xxx的窗口，就在此窗口打开，若没有则创建一个叫xxx的窗口。可通过window.name来查看当前页面的name,若是iframe，则可以给其设置name属性。

3. 若有download属性，则访问这个页面时会将此页面下载，但是得是同源链接(此处存疑)。

4. rel = noopener  为了解决一个bug 目前未学习。 

## 2.img标签的用法
(作为一名前端工程师的底线：不要让图片变形)

img标签的作用是发出get请求，展示一张图片。

img标签的属性有：

1. src(source),代表文件的存储路径。

2. alt(alternative 可替代的)，当图片加载不出来时，可以通过alt属性的内容给用户提示，而非只显示裂开的图片。

3. width 设置宽度

4. height 设置高度 宽高只设置一个，则图片会自动按照比例改变，若两个都改变则很容易让图片变形。

img标签的事件有 onload / onerror，使用方法如下：

```javascript
若图片id为xxx
xxx.onload = function(){
    console.log('success');
}

xxx.onerror = function(){
    console.log('error');
    xxx.src = "404.jpg";
}
```

通过onerror可以让图片加载失败时给出一张替换图片，增强用户体验。

img标签的响应式:max-width:100%,让图片保持最大宽度，始终适应屏幕即可实现响应式。

## 3.table标签的用法
作用：顾名思义，可以用table来实现表格

<table>
<thead>
<tr>
<th></th>
<th>语文</th>
<th>数学</th>
<th>英语</th>
</tr>
</thead>
<tbody>
<tr>
<th>小红</th>
<td>100</td>
<td>100</td>
<td>100</td>
</tr>
<tr>
<th>小明</th>
<td>100</td>
<td>100</td>
<td>100</td>
</tr>
<tr>
<th>小强</th>
<td>100</td>
<td>100</td>
<td>100</td>
</tr>
</tbody>
<tfoot>
<tr>
<th>总分</th>
<td>300</td>
<td>300</td>
<td>300</td>
</tr>
</tfoor>
</table>

如要实现如图所示的表格代码如下:

```HTML
<table>
    <thead>
        <tr>
            <th></th>
            <th>语文</th>
            <th>数学</th>
            <th>英语</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th>小红</th>
            <td>100</td>
            <td>100</td>
            <td>100</td>
        </tr>
        <tr>
            <th>小明</th>
            <td>100</td>
            <td>100</td>
            <td>100</td>
        </tr>
        <tr>
            <th>小强</th>
            <td>100</td>
            <td>100</td>
            <td>100</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <th>总分</th>
            <td>300</td>
            <td>300</td>
            <td>300</td>
        </tr>
    </tfoot>
</table>
```

注意点：

1. thead、tbody、tfoot三者之间可以互换位置，但最后页面显示永远是按照头身体脚的顺序显示。
2. 若直接写tr、td则浏览器自动纠错，会默认将其放入tbody内。
3. 相关的样式有  table-layout：auto/fixed,auto为默认值，会根据列值的长度改变，而fixed会使不同的列较均衡。border-spacing,表格间隔，border-collapse:collapse,表格合并。


## 4.多多练习

