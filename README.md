# **Aiqiyi-Sign**

> 爱奇艺会员签到打卡
>
> 爱奇艺会员签到打卡，增加经验值，增加爱奇艺会员天数（连续打卡一个月，可以增加5天会员），**前提是爱奇艺会员**
>每日三次抽奖，非会员也可参与
> 项目地址：[Aiqiyi_Sign](https://github.com/ioutime/Aiqiyi_Sign)


## 脚本功能：mm 

1. 登录爱奇艺,cookie（需要手动获取）
2. 支持爱奇艺会员**签到**打卡，每日三次**抽奖**，并显示今日成长值，vip到期时间等
3. 支持本地命令行执行
4. 支持pushplus 微信公众号推送
5. 支持腾讯云函数部署（建议，推荐）
6. 支持多个账户签到（P00001)，只支持签到，无其他功能


## 注意事项：

- **需要是爱奇艺会员**，否则脚本执行会不成功

  

使用方法:
---

### 安装依赖

```shell
pip install -r requirements.txt
```

### 本地执行脚本----local_action.py

**必须**：**替换local_action.py的第十九行为自己的cookie值（下面有获取cookie的方法）**，否则运行不成功

eg:

```shell
python local_action.py
```

结果

```
========================================
*****: 签到成功:获得积分4 成长值4 累计签到 2 天
网页端签到成功: 获得积分6 累计签到2天
VIP等级:5
升级需成长值:4267
VIP到期时间:2022-02-24
今日抽奖次数:3
第1次抽奖:《我们的父辈1》
第3次抽奖:《我们的父辈1》
第2次抽奖:《我们的父辈1》
执行时间:7.906020096000248
========================================
```



### 部署参数介绍

```
 COOKIE (必填)
 TOKEN (选填,pushplus的token值)	
 P00001(选填，多账号签到使用，注意是四个零; 多个以英文逗号【','】隔开，必须是英文的逗号)
```



### COOKIE值获取

1、打开[爱奇艺](https://www.iqiyi.com/)官网，并***登录***，一定要登录

2、按下**F12**，选择**network**（或者是网络）, 按下 **F5** 刷新页面，如下图所示

<img src="img/2021-7-20 1-1.png"  />

3、点击第一个**www. iqiyi .com**，右边的**Headers**，找到 **Request Headers**，中的cookie值（从冒号开始）

<img src="img/2021-7-20 1-2.png"  />

### pushplus 微信公众号推送

使用[pushplus](http://www.pushplus.plus/)平台进行推送。

使用方法：

1. 访问[pushplus](http://www.pushplus.plus/)官网，登录
2. 找到**一对一推送**，并复制你的**token**
3. 执行脚本时替换token值

<img src="img/2021-7-15 token.png"  />



结果：

```
签到成功
成长值+2
连续签到：3天
签到周期：3天/7天
VIP等级：4
升级需成长值：315
VIP到期时间:2021-10-04
```



腾讯云函数部署：
---

详细过程请看[腾讯云部署.md](https://github.com/ioutime/Aiqiyi_Sign/blob/master/腾讯云部署.md)文件




## 多个爱奇艺账号部署：

多个账号部署，和上**面的部署流程一样**，只是**需要参数不同**不一样。

### 腾讯云函数部署：

填写必要参数 **P00001** 【注意是四个零; 多个以英文逗号【','】隔开，必须是英文的逗号】


P00001的获取与如何填入数据
---

1、打开[爱奇艺](https://www.iqiyi.com/)官网，并***登录***，一定要登录

2、按下**F12**，选择**Application**（或者是应用程序）, 并选择左侧栏的Cookies ,如下图所示

<img src="img/2021-8-4 1-1.png"  />

3、在搜索栏中输入P00001，回车，如下图所示，复制P00001

<img src="img/2021-8-4 1-2.png"  />





## 建议：

1. 建议关注爱奇艺的公众号，能接收到会员天数的增加消息
2. 建议添加微信公众号推送，以便接收是否打卡成功
3. 如果使用cookie签到，网页端登录后别退出一直保持登录，建议一个月更新一次cookie值，**不更新也没事，可以正常签到**，但是不能获取个人详细信息（如vip到期时间等）

