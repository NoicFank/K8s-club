# Informer Server 端过滤
 在一些场景下，我们并不希望informer机制将所有对象全部同步到本地，而是在Server端将我们不关心的内容过滤掉。
 比如：通过将podInformer的过滤条件置为`spec.nodeName=10.0.0.9`，就可以实现只有nodeName为10.0.0.9
 的pod事件会被监听到。

此处 

