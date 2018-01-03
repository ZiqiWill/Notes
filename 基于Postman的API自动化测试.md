# 基于POSTMan的Api自动化测试

>参考文章：
>
>- [基于Postman的API自动化测试](https://segmentfault.com/a/1190000005055899)
>


##1. Collection
- 每个请求都可以保存到一个Collection中。
- 集合不单可以保存和分类，还支持一建运行整个集合内的测试
- 每个请求看成一个Test Case，那么Collection则可以看成一个Test Suite
- 每个Collection都有一个URL，通过Share可以分享集合，或者用于[Newmen](https://www.npmjs.com/package/newman)执行。
- [Newmen](https://www.npmjs.com/package/newman)是一个命令行工具，可以让POSTman测试添加到持续集成系统中。


2. 