<h1 align="center">RequestTemplate by 1n7erface</h1>

## 首款双语双端内网扫描以及验证工具
快速、准确、全面、利用、检测内网当中存在的漏洞

![](https://img.shields.io/badge/ReaTeam-%E6%AD%A6%E5%99%A8%E5%BA%93-red) ![](https://img.shields.io/badge/version-beta0.0.1-brightgreen) ![](https://img.shields.io/badge/author-1n7erface-blueviolet)

<h3>碰到任何问题直接提issues,在线等bug直修。</h3>

## 项目说明

- 在内网渗透的过程当中,收集网段的连通性往往意味着攻击面的大小。常用的收集网段的命令并不能收集全面，只有爆破才是最全面的解决办法。
- 在内网渗透的过程当中,凭据的复用往往使我们的内网横向事半功倍。使用配置文件的方式配置密码字典效果显著。
- 使用xray的poc对内网的web服务进行漏洞扫描。
- 内置默认字典爆破FTP、Memcached、MongoDB、MySQL、Oracle、Postgres、Redis、SMB、MSSQL、SSH、17010的检测。
- 使用java语言对漏洞进行复现，验证，后利用。

## 使用必读

- 程序当中默认内置弱口令字典,config.json中配置的user和pass的字典针对于信息收集到的复杂密码,放置与扫描端同目录下即可。
- 如果内网连通网段过于多,不建议使用全网段自探测加扫描,耗费时间过长,如家庭网和政务网。
- java端的代理配置账号密码存在问题,兼容性会在后续版本完善,目前版本的隧道不能使用认证。


## 使用说明


> 常见的参数

```shell
App 不加参数对192，10，172网段进行探测扫描
```

```shell
App -i 192.168.1.1/24  指定c段进行扫描
```

```shell
App -c 192 对192连同网段进行扫描,10和172同理
```

```shell
App -a true 对存活网段进行探测
```
```shell
将扫描的结果output文件导入java端内
```

<img width="921" alt="image" src="https://user-images.githubusercontent.com/52184829/161315973-0229f31b-ec32-498c-9617-8e76fdf0bea1.png">
<img width="800" alt="image" src="https://user-images.githubusercontent.com/52184829/161316094-825ce6f0-a35e-44db-81b6-ea19f2ba0193.png">
<img width="876" alt="image" src="https://user-images.githubusercontent.com/52184829/161316171-44ce4ae5-5265-46ab-910d-7a7bf8e6d590.png">

## 感谢！

感谢@shadow1ng 师傅对扫描端的疑问解惑。
https://github.com/shadow1ng/fscan

感谢@j1anFen 师傅的项目对服务端的参考。
https://github.com/SafeGroceryStore/MDUT

## 最后 

也可以关注我的公众号
![扫码_搜索联合传播样式-白色版](https://user-images.githubusercontent.com/52184829/161317011-343af6a1-0387-4b6b-9553-cbeebd91e33d.png)


