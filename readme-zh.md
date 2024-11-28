语言(Language):   

| 简体中文（本页）                          | [English(en)](https://github.com/Picodesu/xiaoxiao_arm64-v8a/blob/main/readme-en.md) |
| --------------------------------- | ------------------------------------------------------------------------------------ |
| Simplified Chinese(zh-Hans/zh-CN) | [英语](https://github.com/Picodesu/xiaoxiao_arm64-v8a/blob/main/readme-en.md)          |

# xiaoxiao_arm64-v8a
## 为校校app添加arm64-v8a ABI so文件以支持64位系统便于在最新的纯64位设备与系统上运行。
- 校校app官方包名:com.www784035275.ofy
- 本仓库非官方仓库，亦非开源仓库。仓库中的文件仅供学习交流使用，未经原作者许可不得商用，下载后请在24小时内删除。*
- 多网页:Github（本站）、[Gitee](https://gitee.com/picodesu/xiaoxiao_arm64-v8a)、[GitCode](https://gitcode.com/Picodesu/xiaoxiao_arm64-v8a/overview)
- 修改包名、签名，以防系统误报人工亲测无法安装和病毒。
## 1.支持哪些设备？
- 仅支持arm芯片搭载Android系统（包括华为鸿蒙4.x及之前）的设备(常见芯片厂:高通骁龙、联发科天玑、华为海思）
- 其余设备可以通过安装[aida64](https://www.aida64.com/downloads/latesta64droid )(点击下方含"EU"或"US"的超链接下载)或[设备信息by流舟](https://www.coolapk.com/apk/com.liuzh.deviceinfo)查看芯片/支持的ABI，只要有arm64-v8a(64位）、armeabi(32位）中至少一个就可以使用。如果你这两个软件都无法正常安装并打开，本软件自然也是不能安装的。
- 未在无兼容层的纯64位设备(如魅族21)测试，可以安装的设备以实际使用为准，不对修改可能造成的影响负责。
## 2.我应该下载哪个安装包？
- 官方包为[xiaoxiao_armeabi_official_mirror.apk](https://github.com/Picodesu/xiaoxiao_arm64-v8a/releases/download/0.2.67.64b.1/xiaoxiao_armeabi_0.2.67_origin_mirror.apk)，是[官方链接](https://www.5ic.net.cn/xiaoyuan/downApp)的安装包，支持32位(armeabi)的设备请优先使用官方包。
- [both为32位64位兼用包](https://github.com/Picodesu/xiaoxiao_arm64-v8a/blob/main/xiaoxiao64B_both_0.2.67_signed.apk)，由系统选择调用哪个ABI(可通过[LibChecker](:https://github.com/LibChecker/LibChecker)查看 ，如果调用异常或嫌弃兼用包太大可手动安装[64位分包(arm64-v8a)](https://github.com/Picodesu/xiaoxiao_arm64-v8a/releases/download/0.2.67.64b.1/xiaoxiao64B_arm64-v8a_0.2.67.b.1_signed.apk)或[32位分包(armeabi)](https://github.com/Picodesu/xiaoxiao_arm64-v8a/blob/main/xiaoxiaoB_armeabi_0.2.67_signed.apk)，同签名安装不会丢失数据(虽然也没什么数据可丢)。
## 原作者相关信息:
- 根据官方包签名，ta的QQ是784035275，对应邮箱 784035275@qq.com
- 根据whois查询，提供软件网络下载和服务的网站 www.5ic.net.cn 注册者为夏涛老师，对应邮箱 xiatao@mail.buct.edu.cn
## arm64-v8a所用so文件源:
仓库中已放对应so文件，也可自行溯源下载打包。
### libjcore216.so
- 属于极光推送SDK(v3.3.8 2019-10-17到v3.4.0 2019-11-15,下一版本v3.4.1 2019-11-26起使用不同so 文件），[官网](https://www.jiguang.cn/sdk-download） 已不可下载。
- 受[Github搜索结果](https://github.com/Behavior-speaks-loader/Behavior-speaks-loader/blob/5771d0793bb012ba1dde1d3a6ff57f73375fa967/Dataset/dataset/140fd50752a72863cea13f6c1b460cf79a88353a9ee8e1361d000c34f34a62dc/140fd50752a72863cea13f6c1b460cf79a88353a9ee8e1361d000c34f34a62dc_behavior.txt#L631)（631行）启发，从互联网下载的[com.rjjmc.newscratch](https://m.87g.com/az/105746.html)提取
### libRongIMLib.so、libRongRTCso.so、libsqlite.so
- 属于[融云SDK](https://www.rongcloud.cn/devcenter?type=sdk)。根据libjcore216.so时间估计，选用2.10.4 Stable版本，[官网已不再维护2.x版本](https://doc.rongcloud.cn/im/Android/2.X/prepare)，并且不提供下载。
- libsqlite.so :Android系统自带同名so文件，位于system/lib和system/lib64，发现融云SDK中自带后未使用。[SQLite官网](https://sqlite.org/download.html)提供的aar文件中so文件为libsqliteX.so。
- 提供的版本下载自[互联网](http://m.pipikun.com/xiazai/6261.html)。( 下载页所注iOS可能有误，5.x的iOS SDK不含so文件)
### libsec.so
- 下载自[AgoraIO/APICloud-SDK/](https://github.com/AgoraIO/APICloud-SDK/tree/0e9b924eceaa8bece8f86f71fea40c1b07bbb8f9/Android/app/src/main/jniLibs)
- 并不是所有同名so文件都能用。
## - 获取签名文件/侵权需要下架仓库
请原作者使用“原作者相关信息”中提及的邮箱联系。联系方式: 电子邮箱:scrt_19216801@outlook.com 。除此之外，非官方域名邮件、非相关人士不可获取签名、联系下架仓库。
## 除此之外
1. 所有权利归原作者所有。经过原作者同意的使用不必告知，未经过原作者同意的商用告知了也没用。 
2. 下载软件、分发软件或克隆仓库则说明您同意在该过程中遵守中华人民共和国(尤其是中国大陆)有关法律。若您不同意，则勿下载分发克隆本仓库内容。