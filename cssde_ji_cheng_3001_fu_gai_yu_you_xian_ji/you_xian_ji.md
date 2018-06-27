### 优先级

**CSS 优先级法则：**

A  选择器都有一个权值，权值越大越优先；

B  当权值相等时，后出现的样式表设置要优于先出现的样式表设置；

C  创作者的规则高于浏览者：即网页编写者设置的CSS 样式的优先权高于浏览器所设置的样式；

D  继承的CSS 样式不如后来指定的CSS 样式；

E  在同一组属性设置中标有“!important”规则的优先级最大

F 声明位置：

          外部样式（css文件） &lt; 内部样式（页面中style） &lt; 内联样式

G 后引入的优先级高

* **权重**

![http://images.cnblogs.com/cnblogs\_com/xugang/WindowsLiveWriter/CSS\_148B3/jc6\_002\_thumb.png](../assets/httpimagescnblogscomcnblogsc.png)

| h1 {color:blue;} | 1 |
| --- | --- |
| p em {color:purple;} | 1+1=2 |
| .apple {color:red;} | 10 |
| p.bright {color:yellow;} | 1+10=11 |
| p.bright em.dark {color:brown;} | 1+10+1+10=22 |
| \#id316 {color:yellow} | 100 |

* **例外： !important**

**使权重升级到最高，若有多个!important 则后声明的覆盖前面的。**

CSS引入顺序及声明的权重决定了最终采用哪个样式。（总有例外：!important）。

