# HeytapTask
欢太商城自动签到脚本

脚本来源于[hwkxk/HeytapTask](https://github.com/hwkxk/HeytapTask)
修改部分代码为此项目添加腾讯云函数支持以及使用说明

## 已实现功能

* [x] 每日签到
* [x] 每日浏览商品任务
* [x] 每日分享商品任务
* [x] 每日点推送任务
* [x] 狂撒百万积分-任务&转盘
* [x] 天天积分翻倍
* [x] 我的-赚积分-任务&转盘
* [x] 超级会员日转盘
* [x] 智能生活-0元抽奖-宠粉转盘(可能此活动中奖率低!)
* [x] realme宠粉计划转盘(谢谢惠顾概率过高，已默认注释)
* [x] OPPO-0元赢积分
* [x] 可选 钉钉通知、Tg通知、pushplus推送加、企业微信、Bark通知、IFTTT通知 功能

## 使用注意
* 部分域名屏蔽境外IP访问，所以本项目不适于在 非中国IP代理网络下 / Github Actions / 境外VPS 上运行!
* 不要fork后将个人信息填写到自己仓库`config.ini`文件中，请下载到本地编辑，以免隐私泄露。
* cookies 和 User-Agent 信息请自行在手机登录 `欢太商城` APP后使用HttpCanary等抓包工具获取！
> (具体抓包方式请百度/Google)

## 使用说明

### 本地执行
> 本项目使用 python3 实现
#### 1、下载本项目-[点此下载](https://codeload.github.com/QiYueYiya/HeytapTask/zip/refs/heads/main)
#### 2、解压后用文本编辑器 打开`config.ini`按注释说明进行填写
#### 3、需要安装的依赖
```
pip install requests 
```
#### 4、执行方法 命令行or终端 转到程序源码目录下 执行
```bash
 python index.py
```
### 腾讯云函数
#### 1、下载本项目-[点此下载](https://codeload.github.com/QiYueYiya/HeytapTask/zip/refs/heads/main)
#### 2、转到[腾讯云函数](https://console.cloud.tencent.com/scf/index?rid=1)，在[函数服务](https://console.cloud.tencent.com/scf/list?rid=1&ns=default)里点击新建
#### 3、创建方式选择[自定义创建]，[函数名称]请自行命名，[运行环境]选择“Python3.6”，[提交方法]选择“本地上传zip包”，然后点击“上传”，上传本项目代码压缩包
#### 4、[高级配置]-[执行超时时间]设置为900秒，[触发器配置]请自行定义
#### 5、进入刚刚创建的云函数，点击[函数代码]，选中“config.ini”文件，填入欢太商城的Cookies和User-Agent

## 通知推送方式

### 1.钉钉机器人

钉钉群组自定义机器人，但是稳定性高，使用方式参考如下：[钉钉自定义机器人使用方式](https://developers.dingtalk.com/document/app/custom-robot-access)

注意安全设置部分，选择自定义关键词，填写`HeytapTask`，选择加签的在配置文件dingtalksecret填入密钥。

### 2.TgBot机器人

类似于钉钉机器人，只需要一个`token`和`userId`，自行搜索这两个参数的获取方式，自带一个tghost代理转发(可在墙内使用) [自建教程](https://shimo.im/docs/JD38CJDQtYy3yTd8/read)

### 3.pushplus机器人

类似于钉钉机器人，只需要一个`token`，参考[获取pushplus的token](http://www.pushplus.plus/login?redirectUrl=/message)。

注意，升级到了新接口，要重新申请`token`。详情见：[更新推送加推送接口](https://github.com/srcrs/UnicomTask/issues/134)

### 4.企业微信应用通知

企业微信自建应用，可发送消息，并且可以不借助第三方，将消息转发到普通微信。

用电脑，进行[企业微信登录](https://work.weixin.qq.com/wework_admin/loginpage_wx)，普通微信扫码也可登录，，按照[此教程](https://note.youdao.com/ynoteshare1/index.html?id=351e08a72378206f9dd64d2281e9b83b&type=note#/)获取需要的三个值。

### 5.IFTTT通知

通过触发IFTTT的Webhook Trigger来通知到其它任意服务，具体可以参照[IFTTT文档](https://ifttt.com/maker_webhooks)。

### 6.Bark通知

类似于钉钉机器人，只需要一个`Key`，IOS安装Bark即可获取Key[使用文档](https://github.com/Finb/Bark/blob/master/README.md)



## 申明

* 本项目仅用于学习研究，禁止任何人用于商业用途，本人不保证其合法性，准确性，完整性和有效性
* 本人无法100%保证使用本项目之后不会造成账号异常问题，请根据情况自行判断再下载执行！否则请勿下载运行！
* 如果任何单位或个人认为该项目的脚本可能涉及侵犯其权利，则应及时通知并提供相关证明，我将在收到认证文件后删除相关脚本.

## 参考及引用

* [srcrs/UnicomTask](https://github.com/srcrs/UnicomTask)，参考了此项目的结构及推送notify.py代码的引用
