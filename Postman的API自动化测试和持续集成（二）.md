# 基于PostMan的Api自动化测试和持续集成（二）

>参考文章：
>
> - [【基于Postman的API自动化测试】](https://segmentfault.com/a/1190000005055899)
> - [【接口自动化之Postman+Newman】](http://www.cnblogs.com/zuoshaowei/p/6192863.html)
> - [【使用postman作为rest api自动化测试工具】](https://segmentfault.com/a/1190000008279947)

----------

> 接上一篇 [【基于PostMan的API自动化测试和持续集成】](https://github.com/ZiqiWill/Notes/blob/master/Postman%E7%9A%84API%E8%87%AA%E5%8A%A8%E5%8C%96%E6%B5%8B%E8%AF%95%E5%92%8C%E6%8C%81%E7%BB%AD%E9%9B%86%E6%88%90.md)

# Newman
> 基于Postman，Newman是一个专门用来运行Postman Collection脚本的CLI工具。
> 
> 官方地址：[Newman](https://www.npmjs.com/package/newman)

## 1. 安装
- Newman基于 NodeJS，所需需要提前配置NodeJS环境。
- > ensure that you have NodeJS >= v4. A copy of the NodeJS installable can be downloaded from https://nodejs.org/en/download/package-manager.
- 