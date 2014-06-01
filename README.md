# UPS 是一个又拍云服务的简化版服务器端

一个又拍云服务的模拟器，提供与又拍云相同的接口，
开发人员可部署在测试环境中，以与正式环境的又拍云服务隔离。

可使用笔者的另一个项目 UPC[http://upyun.gitcafe.com/likang/upc-for-UPYUN] 
进行管理测试。


## 特色功能

1. HTTP REST 接口几乎与官方完全一致（除部分报错信息）
2. 支持图片处理接口（依赖 Pillow ）
3. 支持 FORM 接口（未进行完整测试）
4. HTTP 服务不依赖任何 第三方库
5. 支持 Python 2 / Python 3
6. 针对本地空间对规则做了一些调整，如空间大小控制等

## 安装

```
pip install ups
```

注意：UPS 依赖 Pillow(亦即 PIL), 而此软件包需要本机有 libjpg / libpng 等库才能更好
的工作， 请首先确认本机已有这些图片处理库。如果确实这些库，又已经把 Pillow 安装好了，
可以尝试 pip uninstall pillow 卸载后，安装上面所指的库，然后重新 pip install pillow。

## 使用

保存如下示例的文件到个人目录的 .upsrc 文件中 （支持多个 bucket ）

```
[server]
host=127.0.0.1
port=8080

[your-bucket-name]
username=foo
password=bar
path=/nfs/images
form_secret=testkey

```

然后直接运行
```
$ ups
```

此时可以用其他客户端工具连接服务，测试服务可用性，具体使用文档不必细表，
与官方一致即可.


## 其他
时间仓促，难免有考虑不周的地方，欢迎扔 issue :D

[github](https://github.com/likang/ups)

[gitcafe](https://gitcafe.com/likang/ups)
