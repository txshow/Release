# 超级影视


### 点播字段

| 字段名称       | 默认值  | 说明   | 其他               |
|------------|------|------|------------------|
| searchable | 1    | 是否搜索 | 0：关闭；1：启用        |
| changeable | 1    | 是否换源 | 0：关闭；1：启用        |
| recordable | 1    | 是否纪录 | 0：关闭；1：启用        |
| playerType | none | 播放器  | 0：系统；1：IJK；2：EXO |
| timeout    | 15   | 播放超时 | 单位：秒             |
| header     | none | 请求标头 | 格式：json          |
| click      | none | 点击js | javascript       |

### 直播字段

| 字段名称       | 默认值   | 说明    | 其他               |
|------------|-------|-------|------------------|
| ua         | none  | 用户代理  |                  |
| origin     | none  | 来源    |                  |
| referer    | none  | 参照地址  |                  |
| epg        | none  | 节目地址  |                  |
| logo       | none  | 台标地址  |                  |
| pass       | false | 是否免密码 |                  |
| boot       | false | 是否自启动 |                  |
| playerType | none  | 播放器   | 0：系统；1：IJK；2：EXO |
| timeout    | 15    | 播放超时  | 单位：秒             |
| header     | none  | 请求标头  | 格式：json          |
| click      | none  | 点击js  | javascript       |

### 样式

| 字段  | 值    | 说明  |
|-------|------|-----|
| type  | rect | 矩形  |
|       | oval | 椭圆  |
|       | list | 列表  |
| ratio | 0.75 | 3：4 |
|       | 1.33 | 4：3 |

直式

```json
{
  "style": {
    "type": "rect"
  }
}
```

横式

```json
{
  "style": {
    "type": "rect",
    "ratio": 1.33
  }
}
```

正方

```json
{
  "style": {
    "type": "rect",
    "ratio": 1
  }
}
```

正圆

```json
{
  "style": {
    "type": "oval"
  }
}
```

椭圆

```json
{
  "style": {
    "type": "oval",
    "ratio": 1.1
  }
}
```

### API

刷新详情

```
http://127.0.0.1:9978/action?do=refresh&type=detail
```  

刷新播放

```
http://127.0.0.1:9978/action?do=refresh&type=player
```  

推送字幕

```
http://127.0.0.1:9978/action?do=refresh&type=subtitle&path=http://xxx
```  

推送弹幕

```
http://127.0.0.1:9978/action?do=refresh&type=danmaku&path=http://xxx
```

新增缓存字符串

```
http://127.0.0.1:9978/cache?do=set&key=xxx&value=xxx
``` 

取得缓存字符串

```
http://127.0.0.1:9978/cache?do=get&key=xxx
```   

删除缓存字符串

```
http://127.0.0.1:9978/cache?do=del&key=xxx
```

### Proxy

scheme 支持 http, https, socks4, socks5

```
scheme://username:password@host:port
```

配置 rules 新增 proxy 判断 host 是否走代理

```json
{
  "name": "proxy",
  "hosts": [
    "api.nivodz.com"
  ]
}
```
