### Vue 的[异步更新队列](https://cn.vuejs.org/v2/guide/reactivity.html#异步更新队列) {#vue-class-style}

Vue.js 默认**异步**更新 DOM。每当观察到数据变化时，Vue 就开始一个队列，将同一事件循环内所有的数据变化缓存起来。如果一个 watcher 被多次触发，只会推入一次到队列中。等到下一次事件循环，Vue 将清空队列，只进行必要的 DOM 更新。在内部异步队列优先使用MutationObserver，如果不支持则使用 setTimeout\(fn, 0\)。

例如，当你设置

`vm.someData = 'new value'`

该组件不会立即重新渲染。当刷新队列时，组件会在事件循环队列清空时的下一个“tick”更新。多数情况我们不需要关心这个过程，但是如果你想在 DOM 状态更新后做点什么，这就可能会有些棘手。虽然 Vue.js 通常鼓励开发人员沿着“数据驱动”的方式思考，避免直接接触 DOM，但是有时我们确实要这么做。为了在数据变化之后等待 Vue 完成更新 DOM ，可以在数据变化之后立即使用

`Vue.nextTick(callback)`

。这样回调函数在 DOM 更新完成后就会调用。

（引自：vue 官网 ，**深入响应式布局**）



