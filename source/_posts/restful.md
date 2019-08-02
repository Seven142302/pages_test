---
title: restful
date: 2019-08-02 18:55:05
tags:
---

## Django发送电子邮件(快速上手版)

> Python里面有自带的发送邮件模块----smtplib 相当方便
> 但是Django也自带了一个轻量级的发送邮件模块(django.core.mail),以便在开发过程中轻松测试电子邮件发送，并为不能使用SMTP的平台提供支持。

#### 快速上手
首先需要在setting里面设置

```python
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_USE_TLS = True #是否使用TLS安全传输协议(用于在两个通信应用程序之间提供保密性和数据完整性。)
EMAIL_USE_SSL = False #是否使用SSL加密，qq企业邮箱要求使用
EMAIL_HOST = 'smtp.qq.com'   
#发送邮件的邮箱 的 SMTP服务器,固定格式,如果是其他的邮箱则是'smtp.xx.com'
EMAIL_PORT = 25     #发件箱的SMTP服务器端口,默认 
EMAIL_HOST_USER = '你的邮箱'    #发送邮件的邮箱地址,
EMAIL_HOST_PASSWORD = '你的邮箱授权码'         #发送邮件的邮箱密码(这里使用的是授权码)
```
[获取授权码的方法(qq邮箱)](https://service.mail.qq.com/cgi-bin/help?subtype=1&&no=1001256&&id=28)
接着在views视图里面就可以发送了

```python
def send(request):
    send_mail (
        'xxxx',# 标题
        'xxxxx.',# 内容
        'xxxxxx@qq.com',# 你的邮箱
        ['xxxxx@163.com'],# 收件人邮箱
        fail_silently=False,
    )
    return HttpResponse('ok')
```