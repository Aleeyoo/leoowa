# 安装 AlistHelper、Alist、Rclone

查看原帖：[⭐【Alist 网盘挂载】超详细 保姆级教程 持续更新 ⭐_alist 挂载小雅网盘最新方法-CSDN 博客](https://blog.csdn.net/Zhudi1145/article/details/140519215)

> 需要下载：
> Alist：[Release v3.42.0 · AlistGo/alist · GitHub](https://github.com/AlistGo/alist/releases/tag/v3.42.0)
> AlistHelper：[Release v0.2.0 · Xmarmalade/alisthelper · GitHub](https://github.com/Xmarmalade/alisthelper/releases/tag/v0.2.0)
> Rclone：[Releases · rclone/rclone](https://github.com/rclone/rclone/releases)

## 打开 AlistHelper 配置

1. 下载 Alist 压缩包，记住解压出的.exe 文件路径
2. 下载 Rclone 压缩包，记住解压出的.exe 文件路径
3. 打开 AlistHelper
4. 在设置中配置相对于的文件地址
5. 重启 Helper，现在可以在首页打开 WebUI
6. 账号默认为admin，密码为随机,可在WebUI中设置，避免每次登录新设备都要随机密码
`Gmeek-html<img src="https://raw.githubusercontent.com/Aleeyoo/note-gen-image-sync/main/26109181-6a17-4526-b756-a76e4f73a7c3.png">`

# 使用Alist挂载多端云盘

## 以夸克网盘为例

1. 挂载路径：/夸克网盘
2. WebDav 策略：本地代理
3. Cookie：网盘界面按下 F12 打开控制台，选择 Network 下的 XHR，刷新，选择带有 cookie 的感叹号图标，复制cookie地址
4. 自选要挂载的文件夹，查看文件夹网址的 path 目录
5. 在浏览器打开要分享文件夹，如 https: //pan.quark.cn/list#/list/all/`地址`
6. 自定义排序方式
7. 保存，查看工作状态
## 其他查看[Alist官方文档教程](https://alistgo.com/zh/guide/drivers)

# 下载安装 RaiDrive

官网：[RaiDrive - 像 USB 驱动器一样安装云存储](https://www.raidrive.com/)

可能出现问题： .NET runtime
> 确保已安装 [.NET(Linux, macOS, and Windows)](https://dotnet.microsoft.com/en-us/download)
> 正确安装依旧报错：
> 查看注册表，Win + r，输入 regedit，回车
> 查看`计算机\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`下注册表地址，对比是否修改
> 确保地址正确，重新安装.NET，不需要重启

`Gmeek-html<img src="https://raw.githubusercontent.com/Aleeyoo/note-gen-image-sync/main/61e4c82c-bb30-47c1-a255-4d850e064a15.png">`


# 配置如图

`Gmeek-html<img src="https://raw.githubusercontent.com/Aleeyoo/note-gen-image-sync/main/298fff07-5ecd-4c9b-a053-32c671f8f085.png">`
`Gmeek-html<img src="https://raw.githubusercontent.com/Aleeyoo/note-gen-image-sync/main/43cd2a9b-631d-469c-809a-e4c2a37dacbc.png">`


# 问题总结

查看原帖：[Windows：AList+RaiDrive 挂载阿里云盘至本地磁盘\_alist 挂载阿里云盘-CSDN 博客](https://blog.csdn.net/qq_55038440/article/details/145441923)

# 进阶技巧

## 通过脚本使 Alist 开机自启动
在 Alist 安装目录下创建一个.vbs 的文件，内容为
```shell
Set Shell = CreateObject("WScript.Shell")
Shell.Run "cmd.exe /k cd ./ && alist server",vbhide
```
创建快捷方式，并放到 C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup 路径下

## 使用任务计划管理器使 RaiDrive 后台静默运行
win 键搜索任务计划管理器，创建任务
配置如下

### 常规：
名称，描述按需求填写
在安全选项中，选择不管用户是否登录都要运行

### 触发器：
开始任务：启动时
高级设置：延迟任务时间 30s

### 操作：启动程序
程序或脚本：粘贴 RaiDrive.exe 文件地址

### 条件：
电源：关闭如果计算机改用电池电源，则停止
