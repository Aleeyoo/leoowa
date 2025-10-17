# ☁️Alist挂载云盘

## 📥前期准备

需下载工具：**Alist v3.42.0、AlistHelper v0.2.0、Rclone**
下载地址：
Alist：[AlistGo/alist GitHub Releases](https://github.com/AlistGo/alist/releases/tag/v3.42.0)
AlistHelper：[Xmarmalade/alisthelper GitHub Releases](https://github.com/Xmarmalade/alisthelper/releases/tag/v0.2.0)
Rclone：[rclone/rclone GitHub Releases](https://github.com/rclone/rclone/releases)

## 🔧AlistHelper配置步骤

1. 解压Alist和Rclone，记录.exe文件路径；
2. 打开AlistHelper，在设置中配置对应文件地址；
3. 重启Helper后打开WebUI（默认账号：admin，随机密码需在WebUI修改）。

`Gmeek-html<img src="https://raw.github.com/Aleeyoo/note-gen-image-sync/main/26109181-6a17-4526-b756-a76e4f73a7c3.png">`

## 🌐挂载云盘示例（夸克网盘）

1. 挂载路径设为 /夸克网盘，WebDav策略选"本地代理"；
2. 获取Cookie：F12打开控制台→Network→XHR→刷新→复制cookie；
3. 自定义排序方式并保存，查看工作状态；
4. 其他网盘参考[Alist官方文档](https://alistgo.com/zh/guide/drivers)。

# 💻 RaiDrive安装与配置

官网下载：[RaiDrive - 像USB驱动器一样安装云存储](https://www.raidrive.com/)。
常见问题：[若提示.NET](http://xn--o0uq09bd6g.net/) runtime错误，需安装[.NET运行时](https://dotnet.microsoft.com/en-us/download)，必要时检查注册表路径。

> 正确安装依旧报错：
> 查看注册表，Win + r，输入 regedit，回车；
> 查看`计算机\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`下注册表地址，对比是否修改；
> 确保地址正确，重新安装.NET，不需要重启。

`Gmeek-html<img src="https://raw.github.com/Aleeyoo/note-gen-image-sync/main/61e4c82c-bb30-47c1-a255-4d850e064a15.png">`

配置如图：

`Gmeek-html<img src="https://raw.github.com/Aleeyoo/note-gen-image-sync/main/298fff07-5ecd-4c9b-a053-32c671f8f085.png">`

# 😋最终效果

`Gmeek-html<img src="https://raw.github.com/Aleeyoo/note-gen-image-sync/main/43cd2a9b-631d-469c-809a-e4c2a37dacbc.png">`

# 📑问题总结

查看原帖：[Windows：AList+RaiDrive 挂载阿里云盘至本地磁盘\_alist 挂载阿里云盘-CSDN 博客](https://blog.csdn.net/qq_55038440/article/details/145441923)

# 🚀 进阶技巧

- Alist开机自启：创建.vbs脚本（内容见原文）→生成快捷方式→放入Startup文件夹；

> 在 Alist 安装目录下创建一个.vbs 的文件，内容为
> ```shell
> Set Shell = CreateObject("WScript.Shell")
> Shell.Run "cmd.exe /k cd ./ && alist server",vbhide
> ```
> 创建快捷方式，并放到 C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Startup 路径下

- RaiDrive后台运行：任务计划管理器创建任务，配置启动时延迟30秒运行，电源选项设为"使用电池时停止"。

> win 键搜索任务计划管理器，创建任务
> 常规：名称，描述按需求填写在安全选项中，选择不管用户是否登录都要运行
> 触发器：开始任务→启动时高级设置→延迟任务时间 30s
> 操作：启动程序→程序或脚本→粘贴 RaiDrive.exe 文件地址
> 条件：电源→关闭如果计算机改用电池电源，则停止
