### MutationObserver {#mutationobserver}

Mutation Observer（变动观察器）是监视DOM变动的接口。DOM发生任何变动，Mutation Observer会得到通知。

Mutation Observer是异步触发，DOM发生变动以后，并不会马上触发，而是要等到当前所有DOM操作都结束后才触发。