# 小程序组件库开发脚手架

需求

打包组件库，差一点，就转换ts代码，然后保留其他文件即可


但是还有一个问题，如何开发调试，实时编译加 npm link，但是这里每次都要进行构建，我擦，如果有一个任务可以进行开发调试就好，自动生成当前开发好的组件到一个example

rollup好像也做不到，它目前只能打包库，多入口可以打包组件库
，


图片资源搞不进去，太复杂了 。

必须要自己写一个

开发思路：

打包的功能

有一个配置文件，配置组件目录，然后进行编译和打包。

打包如何完成？

如何开发？

开发的时候需要监听，自动生成一个小程序目录，用于调试当前组件。

小程序组件库的打包太特殊，不能用传统方式去思考。

例如：小程序引用当前目录的图片，打包工具是分析不到的。

gulp遇到问题，任务都是异步的

不能用复制之后，再去dist目录打包，现在另一条路

src目录

遍历src目录，将所有的文件进行分类，

wxml
less
sass

ts
js

gif
png
jpg

json

然后统一分为不同的任务并发执行

ts单独进行编译转换，js不用理，这样子是最方便快捷的