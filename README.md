# 前言

小程序二次开发，设计UI和修改MD5原帖子已找不到，只有最初的作者的帖子，**作者看到请联系我加上！**
原帖子链接：*[抖音无水印视频下载小程序源码 使用云函数无需购买服务器](https://www.52pojie.cn/thread-1274669-1-1.html)*

## 修改内容

* 1.修改UI
* 2.修改视频下载规则
  * 下载视频需要在后台配置 downloadFile 合法域名，抖音域名频繁更换，导致没有配置的域名不会下载，而后台最对可以配置 200 个，于是用php先把视频下载到自己服务器再用自己的链接返回，只需配一个域名即可！
  * 需搭建php环境，没有服务器的则用内置的下载地址

## 增加内容

* 1.小米运动刷步数
  * 需下载刷步软件配置api，没有服务器的则用内置的api
  * 请访问帖子：*[小米运动刷步数HTTP API服务器](https://www.52pojie.cn/thread-1337151-1-1.html)*

# 使用方法

## 导入项目

导入项目，初始化云开发，不会的看原帖子教程
后台配置域名不需要填抖音的，填自己的，没有则填写图片里的
![后台配置](https://github.com/oddfar/FMiniProgram/blob/master/pics/w-0.png)

## 上传php文件并修改

如果都用我的域名则跳过这步

- 上传“index.php”（刷步数文件）
  * 下载刷步数软件(下载地址在上面)，并挂在服务器上，**把php文件里面的api地址替换成自己的**，修改源码里的链接
  * ![后台配置](https://github.com/oddfar/FMiniProgram/blob/master/pics/w-1.png)
- 上传“q.php”（下载并返回视频链接文件）
  * 修改源码里的链接
  * ![后台配置](https://github.com/oddfar/FMiniProgram/blob/master/pics/w-2.png)
  * 更新云函数文件
  * ![后台配置](https://github.com/oddfar/FMiniProgram/blob/master/pics/w-3.png)
- 上传“del.php”（删除下载视频文件）
  * 默认删除下载10分钟后的视频，加个定时任务访问此文件，否则下载的视频不会被删除，导致服务器磁盘爆满

最后上传发布即可！

# 源码地址

github：**[https://github.com/oddfar/FMiniProgram](https://github.com/oddfar/FMiniProgram)**

## 附言

服务器用的腾讯云学生机，请大佬们手下留情，二次开发和整理资料不易，觉得有用的，请免费评一下分！
