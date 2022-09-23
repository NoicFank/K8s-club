# kube-scheduler 概述

## 简述

## 在pod生命周期中的位置
apiServe -> scheduler


## 插件化配置
kube-scheduler以plugin的方式提供插件化的配置

![framework.png](../images/Scheduler/scheduling-framework-extensions.png)


## 源码剖析

```go
\\ kubernetes/pkg/scheduler/scheduler.go
func (sched *Scheduler) Run(ctx context.Context) {
	sched.SchedulingQueue.Run()
	wait.UntilWithContext(ctx, sched.scheduleOne, 0)
	sched.SchedulingQueue.Close()
}
```
这里最主要的就是`scheduleOne`这个方法，从这里也就可以看出整个k8s内调度的过程是串行单pod的方式，
也就是说所有的pod都是通过`scheduleOne`
