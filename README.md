# freenom-py

## 项目描述 🔑

Freenom 自动续期域名的脚本


## 项目部署 🥳

Python 运行环境
- Windows、Linux、青龙、elecV2P 等


## 使用说明 🕹

<h3><p align="center">🪄 通用版</p></h3>

PC、VPS 等可直接运行，无通知变量

``` sh
wget https://raw.githubusercontent.com/Oreomeow/freenom-py/main/FNplus.py
```
``` sh
python3 FNplus.py -u USERNAME -p PASSWORD
```

`USERNAME`：Freenom 用户名  
`PASSWORD`：Freenom 密码


<h3><p align="center">🐉 青龙邮件版 📧</p></h3>

1. 修改配置文件

``` sh
## ql repo命令拉取脚本时需要拉取的文件后缀，直接写文件后缀名即可
RepoFileExtensions="js py ts html"
```

2. 添加定时拉取任务并运行

```
ql repo https://github.com/Oreomeow/freenom-py.git "FN_extend.py" "" "utils|templates"
```

3. 安装依赖

``` sh
docker exec -it qinglong bash # 进入容器内
```
``` sh
cd /ql/scripts
wget https://raw.githubusercontent.com/Oreomeow/freenom-py/main/requirements.txt -O requirements.txt
pip3 install -r requirements.txt
```

4. 添加环境变量

- 可看[脚本注释](https://raw.githubusercontent.com/Oreomeow/freenom-py/main/FN_extend.py)
- 参考[下方表格](https://github.com/Oreomeow/freenom-py#%E9%82%AE%E4%BB%B6%E7%89%88-)

5. 运行一次 `FN_extend.py` 测试

<h3><p align="center">🪁 elecV2P 邮件版 📧</p></h3>

TASK -> 添加单个任务 -> 修改名称、时间、任务 -> JSMANAGE -> store/cookie 常量储存管理填写[环境变量](https://github.com/Oreomeow/freenom-py#%E9%82%AE%E4%BB%B6%E7%89%88-)

名称：Freenom 续期

时间：cron定时 `25 7 */10 * *`

任务：

```
https://raw.githubusercontent.com/Oreomeow/freenom-py/main/FN_extend.js
```


<h3><p align="center">🐉 青龙消息版 📱</p></h3>

1. 面板添加定时任务，定时随意，运行

```
ql raw https://raw.githubusercontent.com/Oreomeow/freenom-py/main/FNplus.py
```

2. 填写[环境变量](https://github.com/Oreomeow/freenom-py#%E6%B6%88%E6%81%AF%E7%89%88-)

3. 运行一次 `FNplus.py` 测试

<h3><p align="center">🪁 elecV2P 消息版 📱</p></h3>

TASK -> 添加单个任务 -> 修改名称、时间、任务 -> JSMANAGE -> store/cookie 常量储存管理填写[环境变量](https://github.com/Oreomeow/freenom-py#%E6%B6%88%E6%81%AF%E7%89%88-)

名称：Freenom 续期

时间：cron定时 `25 7 */10 * *`

任务：

```
https://raw.githubusercontent.com/Oreomeow/freenom-py/main/FNplus.js
```


## 环境变量 🍒

### 邮件版 📧

| 变量 | 描述 |  示例 |
| --- | --- |  --- |
| FN_ID | Freenom 用户名 | 1234567890@gmail.com |
| FN_PW | Freenom 密码 | 12345678 | 
| MAIL_USER | 发件人邮箱用户名 |  address@vip.qq.com 或 123456@qq.com | 
| MAIL_ADDRESS | 发件人邮箱地址 | address@vip.qq.com 或 123456@qq.com |
| MAIL_PW | 发件人邮箱授权码 | xxxxxxxxxxxxxxxx 看下方链接 |
| MAIL_HOST | 发件人邮箱服务器 | smtp.qq.com 不填默认为这个 |
| MAIL_PORT | 邮箱服务器端口 |  465 不填默认为这个 |
| MAIL_TO | 收件人邮箱可与发件人相同 | address@vip.qq.com 或 123456@qq.com |

- 填写总参考

> [如何设置POP3/SMTP的SSL加密方式？](https://service.mail.qq.com/cgi-bin/help?subtype=1&&id=28&&no=369)

### 消息版 📱

| 变量 | 描述 | 参考 |
| --- | --- |  --- |
| FN_ID | Freenom 用户名，多账号空格隔开| 1234567890@gmail.com  9876543210@enayu.com|
| FN_PW | Freenom 密码，多账号空格隔开| 12345678 87654321|
| BARK | bark 服务 | 此参数如果以 http 或者 https 开头则判定为自建 bark 服务 |
| SCKEY | Server 酱 | |
| TG_BOT_TOKEN | tg 机器人 | |
| TG_USER_ID | tg 机器人 | |
| TG_PROXY_IP | tg 机器人 |
| TG_PROXY_PORT | tg 机器人 |
| DD_BOT_ACCESS_TOKEN | 钉钉机器人 | |
| DD_BOT_SECRET | 钉钉机器人 | |
| QYWX_APP | 企业微信应用 | 参考 http://note.youdao.com/s/HMiudGkb |

- 调用模块

> [notify.py](https://raw.githubusercontent.com/whyour/qinglong/master/sample/notify.py)


## 查看通知 📮

不出意外会收到一封关于域名续期的邮件或者 tg 等通知消息


## 写在最后 🔚

核心代码见 `utils/freenom.py`

此项目核心接口参考 [Freenom-PHP](https://github.com/luolongfei/freenom) 

**感谢不限于以下开发者**

[@shuai93](https://github.com/shuai93)

[@luolongfei](https://github.com/luolongfei)
