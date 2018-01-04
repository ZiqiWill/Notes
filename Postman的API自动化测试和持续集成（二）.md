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
> Newman**基于NodeJS** ，所以 需要提前配置好NodeJS环境。
> 
> **Notes:** ensure that you have NodeJS >= v4. A copy of the NodeJS installable can be downloaded from :
>  https://nodejs.org/en/download/package-manager


- 打开控制台，运行： `npm install -g newman`
- 校验Version，运行：`newman --version` ![version.png](https://www.z4a.net/images/2018/01/04/version.png)

## 2. 执行脚本
- 脚本格式：
> 
`newman run <collection-file-source> [options]`

> 例如:
>
```
newman run demo.postman_collection.json 
--reporters cli,html 
--environment dev.postman_environment.json 
--reporter-html-export result.html

```

- 命令行(cli)结果：
![cliresult.png](https://www.z4a.net/images/2018/01/04/cliresult.png)

## 3. Jenkins 集成：
- 构建选择Execute Windows batch command，输入上面的命令
- 如果上面命令中需要生成Junit的xml测试报告，在构建后可以选择Publish JUnit test result report插件可以用来解析报告。
