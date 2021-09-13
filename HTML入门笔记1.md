# HTML入门笔记1
1.HTML是由 Tim Beners-Lee 发明的，全称为HyperText Markup Language，意为超文本标记语言。

2.HTML在VSCODE中起手应该输入!后点击Tab键，会自动生成HTML结构。

3.常用的表示章节的标签有h1~h6、section、article、main、aside、header、footer等等。

他们各自代表的意思是：

3.1 h1~h6 代表标题，从1到6标题字体大小依次变小。

3.2 header既可以指整个网页的头部，也可以指网页上某篇文章，某个章节的头部。

3.3 footer指的是网页或者文章章节的尾部。

3.4 main代表页面的主体内容，一个页面只能有一个main。main是顶层标签，不能放在header、footer、article、aside等标签中。

3.5 article代表页面中一段完整的内容，一个页面可包含多个article，比如一个页面中同时有多篇文章。

3.6 aside可以认为是对主体内容main的补充。

3.7 section表示一个有主题的独立部分，如在一篇文章中可以表示一个章节。article中可以含多个section。

```HTML
以上标签可做一个整体应用如下
PS：其中的 &copy; 在HTML中代表版权标识
<article>
    <header>头部可能放导航栏或者广告</header>
    <main>
        <h1>这是一篇文章</h1>
        <section>
            <h2>第一章</h2>
            <p>第一章内容</p>
        </section>
        <section>
            <h2>第二章</h2>
            <p>第二章内容</p>
        </section>
    </main>
    <aside>
        aside放文章的补充内容或者广告
    </aside>
    <footer>尾部可能有版权声明 &copy; 版权所有</footer>
</article>
```

4.全局属性有
* class  类名
* contenteditable 可编辑，看到这个页面的用户可以直接在上面编辑
* hidden 隐藏
* id 只能自己记住这个id用过没来确定是否唯一，不到没办法不用
* style 用来设置样式
* tabindex 控制TAB键的顺序，0是最后选到，-1是永远选不到
* title 鼠标悬浮时显示的内容

5.常用的内容标签有

* ol + li 代表有序列表 ol ordered list ， li list item 
* ul + li 代表无序列表 undered list 
* dl + dt + dd 代表描述列表 description list  、description term 、description data 小技巧 使用时可以输入dl+ 之后按Tab键，自动生成结构。
* pre HTML默认多个空格会缩成一个，若某部分内容需要保留空格，则用pre标签将该部分进行包裹。
* hr 水平分割线
* br break  代表换行
* a anchor 锚 代表链接 
* em 代表语气上强调某内容
* strong 代表实质强调的内容
* code 用来包裹代码
* quote 引用  <quote></quote>内联引用  <blockquote></blockquote>块级引用