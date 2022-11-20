# mini-router

> 微信小程序路由器

开发的难点：

api的设计，可以参考，然后根据使用方式进行反推

路由守卫参考vue-router的实现

代码组织方式，先把功能写出来，代码之后再进行去除冗余和抽象、

思路：如何触发导航守卫

导航守卫其实是一个一个异步队列

每次调用push等方法的时候，保存当前的路由对象，保存当前的跳转函数，然后执行执行导航守卫，守卫全部通过就可以去调用保存的跳转函数，进行跳转，这样子就完成了。

上面是前置守卫的，等前置守卫执行完并且跳转函数执行完，再遍历后置守卫即可。

