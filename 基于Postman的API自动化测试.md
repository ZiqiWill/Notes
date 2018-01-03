# 基于POSTMan的Api自动化测试和持续集成

>参考文章：
>
>- [基于Postman的API自动化测试](https://segmentfault.com/a/1190000005055899)
>

----------


## 1. 关于API测试
- Postman测试沙箱 是一个JavaScript执行环境，可以通过JS脚本来编写pre-requist和测试脚本。pre-requist可以用来修改一些默认参数。
- Postman沙箱集成了几个工具库，比如lodash、SugarJs、tv4，还有一些内置函数如xml2JSON。
> [tv4](https://github.com/geraintluff/tv4)是POSTMan集成的一个工具库，通过编写JSON Schema，用来验证JSON数据是否符合一定格式，JSON Schema的语法请[参照这里](http://json-schema.org/example1.html)

## 2. 关于JSON Schema
- JSON Schema 是一种用于验证JSON格式的语法规则。
- [JSONSchema.net](https://jsonschema.net/#/) 在线生成JSON Schema的网页,输入期望的JSON数据，自动根据JSON数据格式分析出对应的JSON Schema。


## 3. Collection
- 每个请求都可以保存到一个Collection中。
- 集合不单可以保存和分类，还支持一建运行整个集合内的测试
- 每个请求看成一个Test Case，那么Collection则可以看成一个Test Suite
- 每个Collection都有一个URL，通过Share可以分享集合，或者用于[Newmen](https://www.npmjs.com/package/newman)执行。
- [Newmen](https://www.npmjs.com/package/newman)是一个命令行工具，可以让POSTman测试添加到持续集成系统中。
