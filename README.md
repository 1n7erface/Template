<h1 align="center">RequestTemplate</h1>

## 首款双语双端内网扫描以及验证工具
快速、准确、全面、利用、检测内网当中存在的漏洞

![](https://img.shields.io/badge/ReaTeam-%E6%AD%A6%E5%99%A8%E5%BA%93-red) ![](https://img.shields.io/badge/version-beta1.0.2-brightgreen) ![](https://img.shields.io/badge/author-1n7erface-blueviolet)

## 项目说明

- 1.网段探测:   检测当前机器连通的网段情况
- 2.横向移动:   多种弱口令爆破模块,可通过同目录下config.json配置
- 3.WEB扫描:   集成Xray三百多种POC检测
- 4.漏洞验证:   使用Java端配置代理对扫描结果进行复现验证截图

## 使用必读

- 程序当中默认内置弱口令字典,config.json中配置的user和pass的字典针对于信息收集到的复杂密码,放置与扫描端同目录下即可。
- 如果内网连通网段过于多,不建议使用全网段自探测加扫描,耗费时间过长,如家庭网和政务网。

## 使用说明

> 常见的参数

```shell
App 不加参数对192，10，172网段进行探测扫描
```
```shell
App -i 192.168.1.1/24  指定c段进行扫描，支持CIDR计算
```
```shell
App -c 192 对192连通网段进行扫描,10和172同理
```
```shell
App -a true 对存活网段进行探测
```
```shell
App -b true 对指定网段进行爆破，不进行web检测。针对场景：搜集凭据->爆破->搜集凭据->爆破，配合config.json文件
```
```shell
App -e true 对整个扫描过程进行输出，将错误的日志也进行打印。通常监控程序出现的异常以及运行顺序。
```
```shell
将扫描的结果output文件导入java端内
```
<img width="915" alt="image" src="https://user-images.githubusercontent.com/52184829/164612773-a16d57df-e647-48b0-9355-888d1b8009fb.png">
<img width="800" alt="image" src="https://user-images.githubusercontent.com/52184829/164612911-704a7629-1c09-4aef-9f89-bc9fa117ba23.png">
<img width="800" alt="image" src="https://user-images.githubusercontent.com/52184829/164612924-26832b7c-efe7-422b-bd90-7a17c3eb404f.png">

## 感谢！

感谢@shadow1ng 师傅对扫描端的疑问解惑。
https://github.com/shadow1ng/fscan

感谢@j1anFen 师傅的项目对服务端的参考。
https://github.com/SafeGroceryStore/MDUT

