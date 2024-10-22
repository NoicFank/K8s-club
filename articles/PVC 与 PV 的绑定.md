
事情的起源是，之后一个




整一个 pvc 和 pv 绑定的过程中是怎么触发的？

1.为什么 pv controller 里面需要使用 pvc/pv cache? 不能使用 lister 吗？

2. 为什么调度器里需要分 pv/pvc 来更新，不能只更新 pvc 吗？

- 会有多个 controller 去操作 pvc 和 pv 的绑定吗？

解绑之后，pv 会被怎么处理？

pvc 和 pv 上面的 finalizer 的意义都是什么？