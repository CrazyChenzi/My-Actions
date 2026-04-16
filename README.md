
<div align="center">
<h1 align="center">My-Actions</h1>
<img src="https://img.shields.io/github/issues/MayoBlueSky/My-Actions?color=green">
<img src="https://img.shields.io/github/stars/MayoBlueSky/My-Actions?color=yellow">
<img src="https://img.shields.io/github/forks/MayoBlueSky/My-Actions?color=orange">
<img src="https://img.shields.io/github/license/MayoBlueSky/My-Actions?color=ff69b4">
<img src="https://img.shields.io/github/languages/code-size/MayoBlueSky/My-Actions?color=blueviolet">
</div>

个人收集并适配Github Actions的各类签到大杂烩

# 项目说明

本项目利用 **GitHub Actions** 实现定时自动签到，目前支持以下平台：

| 平台 | 功能 |
|------|------|
| 哔哩哔哩 (Bilibili) | 每日签到、投币、银瓜子兑换硬币 |
| 爱奇艺 (iQIYI) | 每日签到 |
| 腾讯视频 | 每日签到 |
| 天翼云盘 | 每日签到 |
| 小米运动 | 自动刷步数 |
| 百度贴吧 | 每日签到 |
| 哔咔漫画 | 每日签到 |
| V2EX | 每日签到 |
| 10000 (中国电信) | 每日签到 |

签到结果支持通过多种渠道推送通知，包括微信（Server酱、PushPlus）、Telegram 机器人、钉钉机器人、企业微信、iOS Bark、iGot 等。

# ⚠️ 注意事项与已知弊端

在使用本项目前，请充分了解以下风险和局限性：

1. **账号安全风险**  
   本项目需要将账号密码或 Cookie 存储在 GitHub Secrets 中。虽然 GitHub Secrets 有一定的安全保护，但将敏感凭据托管在第三方平台仍存在一定风险。Cookie 一旦泄露，可能导致账号被盗用。

2. **违反平台服务条款风险**  
   自动化脚本模拟用户操作，可能违反各平台的用户服务协议（ToS）。平台有权封禁检测到异常行为的账号，**使用本项目须自行承担账号被封的风险**。

3. **凭据过期问题**  
   Cookie 和部分 Token 均有有效期（例如爱奇艺 Cookie 约三个月有效期）。过期后需要手动重新获取并更新 Secrets，否则脚本将静默失败或报错。

4. **平台接口变更**  
   各平台可能随时更新 API 接口或加强风控策略，导致脚本失效。脚本维护依赖社区贡献，更新可能存在滞后。

5. **GitHub Actions 定时任务限制**  
   GitHub 规定：若仓库超过 **60 天无任何提交活动**，定时（`schedule`）工作流将被自动停用。需要定期向仓库提交一次变更（如修改 README 加空格）来维持活跃状态。此外，GitHub Actions 每月免费额度有限（公共仓库不限，私有仓库每月 2000 分钟），请注意用量。

6. **依赖 GitHub 服务可用性**  
   本项目完全依托 GitHub Actions 运行，若 GitHub 服务出现故障或政策调整，可能影响签到的正常执行。

7. **无失败重试机制**  
   脚本在网络抖动或平台临时故障时，不会自动重试，该次签到将直接失败。

8. **步数刷取风险（小米运动）**  
   自动刷步数可能被小米运动或关联的微信/支付宝运动检测为异常，存在账号被封禁或步数清零的风险。

## 不要fork了 ⭐️star就行 #

[点这里加TG群](https://t.me/+bCXtiD4YI1ExNjE1) 

需要什么签到可以去提[issues](https://github.com/MayoBlueSky/My-Actions/issues),也欢迎PR

# 使用方式
1. [新建仓库并同步代码](RepoSync.md)
2. 点击Settings -> Secrets -> 点击绿色按钮 (如无绿色按钮说明已激活。直接到下一步。)
3. 新增 new secret 并设置 [Secrets](Secrets.md):
4. 双击右上角自己仓库Star触发，如有不使用项目请[禁用部分项目](https://cdn.jsdelivr.net/gh/BlueskyClouds/Script/img/2020/10/19/img/2020-10-19.jpg)
6. **必须** - 请随便找个文件(例如`README.md`)，加个空格提交一下，否则可能会出现无法定时执行的问题
7. 由于规则更新,同步后会默认禁用,请手动点击Actions 选择要签到的项目 `enable workflows`激活
8. [定时执行](#定时执行) (如修改了执行时间 请关闭同步源仓库  否则同步时会覆盖)

[设置相关Secrets](Secrets.md)

# 定时执行
1. 支持手动执行，具体在Actions中选中要执行的Workflows后再在右侧可以看到Run workflow，点击即可运行此workflow。

2. 如果嫌上一步麻烦的，也可以直接点击一下自己的star，你会发现所有的workflow都已执行。

3. 如需修改执行时间自行修改`.github\workflows\`下面的yaml内的` cron:` 执行时间为国际标准时间 [时间转换](http://www.timebie.com/cn/universalbeijing.php) 分钟在前 小时在后 尽量提前几分钟,因为安装部署环境需要一定时间

### 同步Fork后的代码

#### 手动同步

手动执行一次`同步源仓库`即可
#### 自动同步
开启并启用`同步源仓库`即可 每天会定时同步两次
# 致谢

[@chavyleung](https://github.com/chavyleung/)  
[@Wenmoux](https://github.com/Wenmoux/)  
[@NobyDa](https://github.com/NobyDa/)

# 支持一下

  ![支持一下](https://cdn.jsdelivr.net/gh/BlueskyClouds/Script@master/img/2021/05/25/img/wx.png)
### 访问量

![](http://profile-counter.glitch.me/MayoBlueSky/count.svg)
