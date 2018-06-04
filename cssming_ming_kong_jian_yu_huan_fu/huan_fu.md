### 换肤

网页换肤的基本原理很简单，就是使用 JS 切换对应的 CSS 样式表。例如导航网站 Hao123 的右上方就有网页换肤功能。除了切换 CSS 样式表之外，通常的网页换肤还需要通过 Cookie 来记录用户之前更换过的皮肤，这样下次用户访问的时候，就可以自动使用上次用户配置的选项。

那么基本工作流程就出来了：访问网页——JS 读取 Cookie ——如果没有，使用默认皮肤——如果有，使用指定皮肤；用户点击换肤选项——JS 控制替换对应的 CSS 样式表——将皮肤选项写进 Cookie 保存。

切换方式：

1.  切换body/html 类名
2.  切换样式表文件的引入&lt;link&gt;标签的href

一款基于bootstrap皮肤：

切换皮肤的JS：

皮肤文件的CSS

@import &quot;../elements/elements.less&quot;;

@import &quot;../variables.less&quot;;

/*样式1*/

@smstyle-1-header-color : #22262e;

@smstyle-1-ribbon-color : #e6e6e6;

@smstyle-1-breadcrumb-color : #868686;

.smart-style-1{

a{ transition:color .1s linear 0s,background-color .1s linear 0s!important }

#header { background-image: none; background-color: #22262e; }

}

………

/*样式2*/

.smart-style-2 #header, .smart-style-2 .page-footer, .smart-style-2 .superbox-show {

background-image: none;

background-color: #2C3742;

}

………

/*样式3*/

.smart-style-3 #header {

background-color: #f78c40;

background-image: -moz-linear-gradient(top,#f78c40,#d67632);

background-image: -webkit-gradient(linear,0 0,0 100%,from(#f78c40),to(#d67632));

background-image: -webkit-linear-gradient(top,#f78c40,#d67632);

background-image: -o-linear-gradient(top,#f78c40,#d67632);

background-image: linear-gradient(to bottom,#f78c40,#d67632);

} ………