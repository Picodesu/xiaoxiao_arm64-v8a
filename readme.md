Language（语言）:   

| English(This Page) | [简体中文(zh-Hans/zh-CN)](https://github.com/Picodesu/xiaoxiao_arm64-v8a/blob/main/readme-zh.md) |
| ------------------ | -------------------------------------------------------------------------------------------- |
| 英语                 | [Simplified Chinese](https://github.com/Picodesu/xiaoxiao_arm64-v8a/blob/main/readme-zh.md)  |

# xiaoxiao_arm64-v8a
## Add the arm64-v8a ABI \*.so file to xiaoxiao Application to support only-64-bit systems to run it on the latest only-64-bit devices and systems.
![xiaoxiao_arm64-v8a](/img/xiaoxiao_arm64-v8a.jpg)
- official package name of xiaoxiao application apk:com.www784035275.ofy
- This repository is not an official repository, nor is it an open source repository. The files in the repository are for learning and communication purposes only, and cannot be used commercially without the author's permission, so please delete them within 24 hours after downloading.
- Multi-site:Github(this site),[Gitee](https://gitee.com/picodesu/xiaoxiao_arm64-v8a) and [GitCode](https://gitcode.com/Picodesu/xiaoxiao_arm64-v8a/overview)
- Modify the package name and signature to prevent the system from misrepresenting the inability to install by manual pro-testing or mistake it as virus.
- Issues caused by translation differences are subject to the Chinese text
## 1.What devices are supported?
- Only support devices with ARM structure chips powered by Android (including Huawei HarmonyOS 4.x and before) (common chip makers: Qualcomm Snapdragon, MediaTek, Huawei Hisilicon)
- Other devices can look up the supported ABIs of CPU by AIDA64([Google Play](https://play.google.com/store/apps/details?id=com.finalwire.aida64&hl=en)[Official APK Download](https://www.aida64.com/downloads/latesta64droid) or [DevInfo(by LiuZhou)](https://www.coolapk.com/apk/com.liuzh.deviceinfo)(Click the green button that says "立即下载" to download APK).As long as the device have at least one of arm64-v8a (64-bit), armeabi (32-bit), you can use the app. If you these two software can not be installed and opened properly, this software is naturally also can not be installed.
- Not tested in the pure 64-bit devices without compatibility layer (such as the Meizu 21). The equipment that can be installed is subject to actual use. I refuse to take responsibility for the possible impact of the modification.
## 2.Which APK should I download？
- The official and oringinal APK is [xiaoxiao_armeabi_official_mirror.apk](https://github.com/Picodesu/xiaoxiao_arm64-v8a/releases/download/0.2.67.64b.1/xiaoxiao_armeabi_0.2.67_origin_mirror.apk). It is same apk as the one from [the offical link](https://www.5ic.net.cn/xiaoyuan/downApp).Please prioritize the use of official packages for devices that support 32-bit (armeabi).
- [“both”](https://github.com/Picodesu/xiaoxiao_arm64-v8a/blob/main/xiaoxiao64B_both_0.2.67_signed.apk)means it includes armeabi and arm64-v8a \*.so files. System will choose the appropriate ABI  so that it can run on both 64-bit device and 32-bit device most of the time.(ABI used can be looked up by [LibChecker](:https://github.com/LibChecker/LibChecker) .If your system don't choose appropriately or the apk is much too large for you, you can manully choose to install the [only 64-bit APK(arm64-v8a)](https://github.com/Picodesu/xiaoxiao_arm64-v8a/releases/download/0.2.67.64b.1/xiaoxiao64B_arm64-v8a_0.2.67.b.1_signed.apk)or [only 32-bit APK(armeabi)](https://github.com/Picodesu/xiaoxiao_arm64-v8a/blob/main/xiaoxiaoB_armeabi_0.2.67_signed.apk). APKs installed with the same package name don't lose your data.(Although there is no data to lose.)
## Information about the original author:
- According to the official package signature, ta QQ is 784035275, corresponding to the e-mail 784035275@qq.com
- According to whois query, the website www.5ic.net.cn which provides software network download and service is registered by Tao Xia, and the corresponding email address is xiatao@mail.buct.edu.cn.
## the source of arm64-v8a \*.so files come from
The corresponding \*.so files have been put in the repository, you can also find and package them by yourself.
### libjcore216.so
- It belongs to Aurora/Jiguang Client SDK(from v3.3.8 10.17.2019 to v3.4.0 11.15.2019, next version v3.4.1 11.26.2019 used the diifferent \*.so files.)，[Official website](https://www.jiguang.cn/en/sdk-download） doesn't provide it now.
- Reading [the result of Github search](https://github.com/Behavior-speaks-loader/Behavior-speaks-loader/blob/5771d0793bb012ba1dde1d3a6ff57f73375fa967/Dataset/dataset/140fd50752a72863cea13f6c1b460cf79a88353a9ee8e1361d000c34f34a62dc/140fd50752a72863cea13f6c1b460cf79a88353a9ee8e1361d000c34f34a62dc_behavior.txt#L631)(line 631), I ended up getting it from [com.rjjmc.newscratch](https://m.87g.com/az/105746.html) APK.
### libRongIMLib.so、libRongRTCso.so、libsqlite.so
- They come from RongCloud SDK([Chinese SDK site](https://www.rongcloud.cn/devcenter?type=sdk),[English official site](https://rongcloud.io)。According the estimate time from getting libjcore216.so. I chose the version 2.10.4 Stable. However, RongCloud no longer maintains version 2.x since April 24 [(Chinese Doc)](https://doc.rongcloud.cn/im/Android/2.X/prepare). They don't provide the download page of ver 2.x either.
- libsqlite.so :Android system has a \*.so file with the same name of it, and its parent is system/lib and system/lib64，I didn't use it since I found there is one in RongCloud SDK already. The \*.so provided by arr file on [the SQLite Official site](https://sqlite.org/download.html) is called libsqliteX.so, not libsqlite.so.
- The version provided is from [the Internet(Web in Chinese)](http://m.pipikun.com/xiazai/6261.html).(The "iOS" mentioned in the page might be wrong, iOS SDK of version 5.x doesn't include \*.so file)
### libsec.so
- Downloaded from [Github/AgoraIO/APICloud-SDK/](https://github.com/AgoraIO/APICloud-SDK/tree/0e9b924eceaa8bece8f86f71fea40c1b07bbb8f9/Android/app/src/main/jniLibs)
- Not all file with same name can be used in the app. At least I tried some and they crashed.
## Get signature files/Cancel this repository because it is violate your copyright.
First, you have to be oringinal author or some related regulator. The you can e-mail me at scrt_19216801@outlook.com through the e-mail address in the Column *Information about the oringinal author* or official e-mail address with an official domain name. Others can't do it.
## Besides
1. Original authors reserve all rights. It is not necessary to inform me about the use with the consent of the original author, and it is useless to inform about the commercial use without the consent of the original author. 
2. By downloading software, distributing software or cloning the repository, you agree to abide by the laws of the People's Republic of China (especially mainland China) in the process. If you do not agree, do not download, distribute or clone the contents of the repository.