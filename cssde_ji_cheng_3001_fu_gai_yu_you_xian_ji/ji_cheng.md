## 继承

父元素的规则也会适用于子元素。

* 任何一条与CSS继承值冲突的属性值都会覆盖继承的属性值！！
* 本身带有某种CSS特殊样式的标签不会继承父元素定义的相关样式，即使带\(!important\)

> 如：em，b, i

![](/assets/import12.png)

* 可以继承的属性

> **文本属性：**
>
> _font-family, font-size, font-style,font-variant, font-weight, font, letter-spacing,line-height, text-align, text-indent, texttransform_
>
> **列表属性：**
>
> _list-style-image, list-style-position,list-style-type, list-style_
>
> 其他：
>
> _color, azimuth, border-collapse, border-spacing,caption-side, cursor, direction, elevation,empty-cells, orphans, pitch-range,pitch, quotes, richness, speak-header, speaknumeral,speak-punctuation, speak, speechrate,stress,visibility, voice-family, volume, whitespace,widows, word-spacing_

* **font-size**

font-size是可以被继承的。但是它的方式有一些特别。

Font-size的子类继承的不是**实际值**，而是**计算后的值**。

例子：

```
<p>
    字体大小属性
    <em>继承特性</em>
    的演示代码
</p>
<style>
    // 为p定义字体大小为默认字体的80％。
    p { font-size:80%}
</style>
```



效果：

![](/assets/import13.png)





