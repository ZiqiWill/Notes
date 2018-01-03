# 基于PostMan的Api自动化测试和持续集成

>参考文章：
>
> - [【基于Postman的API自动化测试】](https://segmentfault.com/a/1190000005055899)
> - [【接口自动化之Postman+Newman】](http://www.cnblogs.com/zuoshaowei/p/6192863.html)
> - [【使用postman作为rest api自动化测试工具】](https://segmentfault.com/a/1190000008279947)

----------


## 1. 关于API测试
- PostMan最基础的功能就是发送http请求。填写URL、Params、header、body等就可以发送一个请求，可以满足一些简单的测试需求。
- PostMan测试沙箱 是一个JavaScript执行环境，可以通过JS脚本来编写pre-requist和测试脚本。
- 如果需要登录验证，可以通过Authorization满足需求。
- 另外，PostMan沙箱集成了几个工具库，比如lodash、SugarJs、tv4，还有一些内置函数如xml2JSON。
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


## 4. Runner和外部数据
- PostMan自带Runner功能，用于批量运行脚本，也就是可以运行整个Collection。
- Runner运行时可以使用外部CSV文件，或者JSON文件来指定数据，实现数据驱动测试。
> 示例：
> 
>  1. 新建一个JSON文件如下图所示。  
>  ![PostManJSON文件截图](https://www.z4a.net/images/2018/01/03/PostManJSON.png)
>  
>  2. 在请求中配置变量。
>  请求中变量{{cityID}}，用来获取上述JSON文件中的数据，{{ }}中的名字对应json文件的key，或者scv文件的第一行。
>  ![PostURL.png](https://www.z4a.net/images/2018/01/03/PostURL.png)
>  
>  3. 启动Collection Runner   
>  **注意**：Iterations 表示迭代几次，因为例子中只有两条数据，所以填写2。Delay表示每次之间间隔1000毫秒。
>  ![CollectionRunner.png](https://www.z4a.net/images/2018/01/03/CollectionRunner.png)

##  5. 测试（Tests）和自动化
- 在Tests标签页里面，支持用户使用JS编写自己的测试脚本。
- Tests标签页右侧snippets栏，里面是postman内置的测试脚本，辅助对接口进行测试。
- 对于自动化测试，必须要设置Test脚本，不然即使run也没有意义。

> 示例1：
> 
> tests["Status code is 200"] = responseCode.code === 200; 
>
>  *测试responseCode，也就是测试http状态码是否是200*

> tests['Response time is less than 500ms'] = responseTime < 500;
>
> *测试响应时间是否小于500毫秒*
> 
> 示例2：
> 