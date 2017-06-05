# 平台控制面
====================================
### 
* 一）目录结构
+ACE 				自适应网络通信库和IPC库
+ACEWrapper 		ACE封装库
+AuthMgr			认证进程
+Base				基础库
+Build				环境变量和编译系统
+Configuration		配置
+Contrib			第三方库
+Doc				文档
+include			接口头文件和宏定义
+IPC				进程间通信库
+IPOE				IPOE进程，处理IPOE接入业务
+IPPoolManager		地址池管理
+OAM				基础命令
+Portal				Web强推业务处理
+PPP				PPP协议库，给PPPOE进程使用
+PPPOE				PPPOE进程，处理PPPOE业务接入
+UserMgr			用户管理进程，管理PPPOE和IPOE用户接入
+radiusserver		第三方radius服务器，测试用。
+Platform			WFNOS 平台库

### 
* 二）如何编译
进入Build目录下。source env.sh设置环境变量
1)整体编译
	make debug=1编译debug版本
	make debug=0编译release版本

2)单个进程编译
	make pppoe编译pppoe进程
	make ipoe编译ipoe进程
	
3)所有库编译生成动态链接库。
### 
* 三）打包
修过版本号version.h。
#define MAJOR_VERSION 1
#define MINOR_VERSION 0
#define BETA_VERSION 1
### 
然后执行编译。生成tar报文
目录结构如下：
+bin
	-PPPOE
	-IPOE
	-UserMgr
	-AuthMgr
+libs
	-libACE.so
	-libACEWrapper.so
+logs
	-pppoe.log
	-ipoe.log
	-usermgr.log
	-authmgr.log
+conf
	-bngplatform.cfg


