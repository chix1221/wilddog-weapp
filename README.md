# wilddog-weapp


野狗(wilddog)微信小程序客户端


## 项目地址
https://github.com/WildDogTeam/wilddog-weapp

野狗微信小程序客户SDK
----

## 配置
微信小程序平台不同于web平台，它是一个封闭的平台。对于所有的资源使用微信都有严格的限制。所以，在微信小程序中使用野狗之前需要做一些额外的配置，除此之外，你可以像在其他开放平台一样使用野狗。

### 配置域名白名单

首先，如果想使用野狗数据同步功能和登陆认证的功能你需要在微信小程序管理后台配置域名白名单。路径是 设置>开发设置>服务器配置。由于微信给开发者设置了很多限制，每月只能修改3次，所以修改的时候一定要慎重。为了简化配置，你自需要增加2个域名到白名单：

* socket合法域名 `wss://sdal-wx-nss-1.wilddogio.com`
* request合法域名 `https://auth.wilddog.com`

### 配置AppId和AppSecret

如果你想使用微信的用户账号来登陆野狗，那么你还需要在野狗的管理后台配置微信的AppId 和AppSecret。
你可以在 设置>开发设置>开发者ID 中找到AppId 和AppSecret。之后在野狗后台中打开微信小程序登陆授权开关，并且将Appid 和AppSecret传入即可。

## 将野狗sdk引入到微信小程序中

1. 将wilddog-weapp-all.js 直接放到微信小程序的项目中
2. 使用commonjs引入
```
var wilddog = require('wilddog-weapp-all')
```
3. 初始化

```
var config = {
    syncURL: 'https://<WD-APPID>.wilddogio.com',
    authDomain: '<WD-APPID.wilddog.com>'
}
wilddog.initializeApp(config)
```

完整的API请参考 https://docs.wilddog.com/api/sync/web/api.html


