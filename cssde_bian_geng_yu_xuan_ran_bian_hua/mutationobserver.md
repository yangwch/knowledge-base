### MutationObserver {#mutationobserver}

Mutation Observer（变动观察器）是监视DOM变动的接口。DOM发生任何变动，Mutation Observer会得到通知。

Mutation Observer是异步触发，DOM发生变动以后，并不会马上触发，而是要等到当前所有DOM操作都结束后才触发。

示例：

```
var MutationObserver = window.MutationObserver ||
        window.WebKitMutationObserver || 
        window.MozMutationObserver;

var mutationObserverSupport = !!MutationObserver;
// observer变化回调
var callback = function (records) {
    console.log('MutationObserver callback');
    records.map(function (record) {
        console.log('Mutation type: '+ record.type, ', target: ', record.target.nodeName);
    });
};
// 1 初始一个observer实例，指定回调方法
var mo = new MutationObserver(callback);

var option = {
    'childList': true, 
    'subtree': true
};
// 2 observer方法指定所要观察的DOM元素，以及要观察的特定变动。
mo.observe(document.body, option);

window.onload = init;

function init () {
    if (!mutationObserverSupport) {
        return;
    }
    // DOM - 添加按钮 和 body
    var addBtn = document.getElementById('myButton'),
        body = document.body;
    addBtn.addEventListener('click', function (e) {
        for (var i = 0, j = 100; i < j; i++) {
            var p = document.createElement('p');
            p.appendChild(document.createTextNode(i));
            body.appendChild(p);
            console.log('append child node: ' + i);
        }
    }, false);
}
```

MutationObserver所观察的DOM变动（即上面代码的option对象），包含以下类型：

* childList：子元素的变动
* attributes：属性的变动
* characterData：节点内容或节点文本的变动
* subtree：所有下属节点（包括子节点和子节点的子节点）的变动

> #### Vue如何追踪变化
>
> 当你把一个普通的 JavaScript 对象传给 Vue 实例的 `data` 选项，Vue 将遍历此对象所有的属性，并使用** **[**Object.defineProperty**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty)** 把这些属性全部转为 getter/setter。Object.defineProperty 是 ES5 中一个无法 shim 的特性**，这也就是为什么 Vue 不支持 IE8 以及更低版本浏览器的原因。
>
> 这些 getter/setter 对用户来说是不可见的，但是在内部它们让 Vue 追踪依赖，在属性被访问和修改时通知变化。这里需要注意的问题是浏览器控制台在打印数据对象时 getter/setter 的格式化并不同，所以你可能需要安装 [vue-devtools](https://github.com/vuejs/vue-devtools) 来获取更加友好的检查接口。



