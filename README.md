# freenom-py

## 项目描述 🔑

一个 Freenom 自动续期域名的脚本


## 项目部署 🥳

青龙等

### 1. 环境变量配置  🕹

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
> https://service.mail.qq.com/cgi-bin/help?subtype=1&&id=28&&no=369


### 2. 查看收件箱 📮

不出意外会收到一封关于域名续期的邮件


## 写在最后 🔚

核心代码见 ` utils/freenom.py`

此项目核心接口参考 [Freenom-PHP](https://github.com/shuai93/freenom) 。
