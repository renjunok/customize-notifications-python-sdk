# Customize Notifications Python SDK


## [English](https://github.com/renjunok/customize-notifications-python-sdk/blob/main/README.md)

## SDK
[Golang](https://github.com/renjunok/customize-notifications-golang-sdk)
[Python](https://github.com/renjunok/customize-notifications-python-sdk)

## 开发文档
**如果使用其它开发语言，请参照开发文档**

[开发文档](https://github.com/renjunok/customize-notifications-golang-sdk/blob/main/api-doc-en.md)

## 说明
"我的通知"是一个可以让用户给自己发送自定义消息的App应用，供开发人员、运维人员或初创团队发送自定义推送消息的手机使用。

<img src="https://github.com/renjunok/customize-notifications-golang-sdk/raw/main/images/customize-notifications-app-home-view-en.png" width="50%" height="50%" alt="customize notification app home view">
<img src="https://github.com/renjunok/customize-notifications-golang-sdk/raw/main/images/customize-notifications-app-message-detail-view-en.png" width="50%" height="50%" alt="customize notification app message detail view">

## 使用场景
在代码中集用并调用接口后，将给本应用推送一条你自定义的消息，常见使用场景如:
- 程序运行发生错误
- 客户订单处理
- 服务器CPU占用率过高等
- 关注的内容更新等

## 消息类型
1. ![primary](https://via.placeholder.com/15/2463EB/000000?text=+) `常规消息(primary)`
0. ![success](https://via.placeholder.com/15/c5f015/000000?text=+) `成功消息(success)`
0. ![info](https://via.placeholder.com/15/FCD34D/000000?text=+) `提示消息(info)`
0. ![warning](https://via.placeholder.com/15/DF933B/000000?text=+) `警告消息(warning)`
0. ![fail](https://via.placeholder.com/15/f03c15/000000?text=+) `失败消息(fail)`

## 应用
[iOS Store]("https://apps.apple.com/us/app/my-notice-customize-notice/id1566837067")

## 运行环境
> - Python 3.0+

## 安装
> - `pip install custom-notifications`

## 使用方法
> - iOS用户在AppStore商城安装App应用
> - 打开应用后点击左上角菜单获取配置信息, ID 和 Secret
> - 在你需要自定义通知信息中执行下列代码
```python
    try:
        m = Message(title="test title", msg_type=0, content="test content", group="test group")
        m.send_message("your_id", "your_secret")
    except Exception as e:
        print(e)
```

## 注意事项
- title, content, msgType 字段必填, group选填
- title字符数最大值100, content最大值4000, group最大值20
- msgType类型分别为 0 primary, 1 success, 2 info, 3 warning, 4 fail
- 接口调用速率1分钟内最多三次，超出调用的请求不处理
