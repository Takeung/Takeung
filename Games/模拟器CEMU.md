> 摘自：https://zhuanlan.zhihu.com/p/396798396

## 1-1 首先是【模拟器cemu】

**1-1-1下载**的官方地址：[Cemu Emulator](https://link.zhihu.com/?target=https%3A//cemu.info/index.html) 点击下方 Dowload latest version 按钮即可下载

![img](https://picx.zhimg.com/80/v2-6406213d48d3c070a5da6c7026c3777b_1440w.webp)

下载页面

下载下来的是.zip 结尾的压缩文件，通过解压，再点击cemu即可完成安装。



**1-1-2 模拟器的【配置】：**【图形插件】+【cemu-hook】

【**图形插件**】可以通过“**选项**”——“**图形插件**”（第二项）在[右下角](https://zhida.zhihu.com/search?q=右下角&zhida_source=entity&is_preview=1) 点击“**下载最新社区图形插件**”，其过程很简单，但可能图形[插件](https://zhida.zhihu.com/search?q=插件&zhida_source=entity&is_preview=1)网站网络有点卡，可能要多点几次。

【**cemu-hook**】，官方地址：[a plugin for the Wii U emulator](https://link.zhihu.com/?target=https%3A//cemuhook.sshnuke.net/) ，**注意下载和 cemu匹配的版本**，如“Cemu hook 0.5.7.3 for **1.12.1-1.25.0**”1.12.1-1.25.0 就是指对应的cemu版本号。文件解压后，直接复制进 cemu安装目录即可。

![img](https://picx.zhimg.com/80/v2-0dac07b7ab2f9b7a3d6f1c55a3877069_1440w.webp)

------

## 1-2 接着就是 【下载游戏】

我用的是**FunKiiU**，运行下载脚本的方法。有两个好处，**其一**脚本是git下的 开源，**其二** 脚本是通过官方渠道下载的 游戏文件，没有乱七八糟的。

**1-2-1下载FunKiiU脚本 官方网站**：[https://github.com/llakssz/FunKiiU](https://link.zhihu.com/?target=https%3A//github.com/llakssz/FunKiiU) 如图分两步点击，可以下载整个文件夹。当然在这之前电脑得先 安装PYthon，也非常简单，这里略过。

![img](https://pic3.zhimg.com/80/v2-c1c17feea01a6dcc89f3d8afc7bdfbfe_1440w.webp)

**1-2-2 用命令行cmd，运行FunKiiu.py** 来下载游戏。**看着很难，其实很简单**。

在这之前先得知道游戏的【**Title ID**】和【**Title key**】，由于github的源断了，我又重新找了个 提供信息的网站，[https://www.wiiuemulator.com/Game-Key-Database.htm#search](https://link.zhihu.com/?target=https%3A//www.wiiuemulator.com/Game-Key-Database.htm%23search) 可以搜索 三个区的信息。

然后打开cmd，输入**FunKiiu.py 所在的硬盘盘符，**比如我的在D盘的FunKiiU-master文件夹。随便从网站上查询得欧版的 马里奥赛车8信息如下

| name         | Title ID         | Title Key                        |
| ------------ | ---------------- | -------------------------------- |
| MARIO KART 8 | 000500001010ed00 | 32efa28edf2adf16990a175263ba84db |

则可以填写：python FunKiiU.py -title 【**Title ID**】 -key 【**Title key**】, 的格式，**回车即下**

![img](https://picx.zhimg.com/80/v2-407ae99feff46585ec621b3fc74f2e85_1440w.webp)

下载完成之后会在 [FunKiiU.py](https://link.zhihu.com/?target=http%3A//funkiiu.py/) 所在的文件夹 创建一个instal文件夹，点开就能看到一个以【**Title ID**】命名的文件夹。里面装着很多文件，其共同组成一个**WUP格式** 的游戏，为了能够玩耍，需要将其 **转换**（解密）成 **loadiine**格式。



**1-2-3 转换下载的WUP → Loadiine 格式的游戏文件**

**准备[开源软件](https://zhida.zhihu.com/search?q=开源软件&zhida_source=entity&is_preview=1) 【CDecrypt**】 官网：[https://github.com/VitaSmith/cdecrypt/releases](https://link.zhihu.com/?target=https%3A//github.com/VitaSmith/cdecrypt/releases) 下载解压得到 cdecrypt.exe.

然后找到刚才下载好的，以【**Title ID】命名的文件夹，整个拖到**cdecrypt.exe 这个软件图标上面，然后会激活 cmd 自己跑代码，跑完代码就会在 【**Title ID】命名的文件夹**内生产 三个文件夹。

**1-2-4 加载游戏文件**

**这三个文件夹就是 能被cemu 认识的游戏文件**，我们随便新建一个文件夹，将三个文件夹拖进去，然后打开cemu [模拟器](https://zhida.zhihu.com/search?q=模拟器&zhida_source=entity&is_preview=1)本体，点击“选项”——"通用设置"——"游戏路径" 选择添加 包含三个文件夹的 新建文件夹。然后游戏就会被自动读取。

![img](https://pic4.zhimg.com/80/v2-4edb02edde649715604665cee0e8d897_1440w.webp)

## 完结

通过**1-1** 和**1-2** 的操作，一切正常的话，就能顺利进入游戏。



## 后记：

其实到上面两步，教程算是完成了，**但是网上很多教程都会教各种调试，其实我们可以把游戏运行想象成树干，那么实现各种功能就是生长出树枝，是另外一个话题**，如果刚开始就奔着树枝去，而且树枝树干不分的，那么最后很可能会 很受打击，树枝树干都给放弃的结局。

不妨将接下来的操作分为，【实现手柄控制的功能】，【实现帧率和分辨率锁定的功能】，【实现中文汉化的功能】，等等这些可以慢慢研究。

实测我的马里奥3D世界 和马里奥赛车，可以稳定在60帧，1080p的画质。游戏基本无卡顿，只有[马里奥赛车](https://zhida.zhihu.com/search?q=马里奥赛车&zhida_source=entity&is_preview=1) 每次加载新场景的时候会卡顿，但也只是加载第一次，接下来就没问题。