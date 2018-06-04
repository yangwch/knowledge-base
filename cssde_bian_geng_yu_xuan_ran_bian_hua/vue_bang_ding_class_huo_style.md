### Vue 绑定class或style {#vue-class-style}

Vue.js 默认**异步**更新 DOM。每当观察到数据变化时，Vue 就开始一个队列，将同一事件循环内所有的数据变化缓存起来。如果一个 watcher 被多次触发，只会推入一次到队列中。等到下一次事件循环，Vue 将清空队列，只进行必要的 DOM 更新。在内部异步队列优先使用MutationObserver，如果不支持则使用 setTimeout(fn, 0)。

（引自：vue 官网 ，**深入响应式布局**）