#合作机构接入说明
主要采用rsa加密的形式进行交互。双加密（即请求、响应、回调、回调响应都进行加密），接入前。合作结构需要提供公钥给我们，我们也会把提供公钥给合作机构。
数据交互使用HTTP JSON格式进行交互
##加密说明

针对数据对象进行加密。并生成 验签串。传递给双方。

##拉取接口请求
请求信息：
参数|名称|值类型|是否可空|备注
---|:--:|---:|---:|---:|
channel|渠道|string|否|渠道会提前分配
version|版本号|string|否|当前版本为v1
method|方法名|string|否|不同的拉取接口有不同的method，用来确认请求的接口
data|数据区json|string|否|加密后的数据信息
sign|签名|string|否|用来验签
channelType|渠道类型|string|否|固定传递 01

例子：

```
{
    "channel":"xxxx",
    "version":"v1",
    "method":"order.push",
    "data":"KSLJDLQOWIEOAKSDKASDNJKANSDJNKASNJDKHSAKHDKASHDKJASKDHKASHDKHJAKHDAKJSDLSAJLDJALSJDLJSALJDLSDJSJDLKJ",
    "sign":"QIXWKSJHDQMMSDNJKQ",
    "channelType":"01"
}
```


##拉取接口响应
响应信息：
参数|名称|值类型|是否可空|备注
---|:--:|---:|---:|---:|
channel|渠道|string|否|渠道会提前分配
version|版本号|string|否|当前版本为v1
respData|数据区json|string|否|加密后的数据信息
respSign|签名|string|否|用来验签
channelType|渠道类型|string|否|固定传递 01

例子：

```
{
    "channel":"xxxx",
    "version":"v1",
    "method":"order.push",
    "respData":"KSLJDLQOWIEOAKSDKASDNJKANSDJNKASNJDKHSAKHDKASHDKJASKDHKASHDKHJAKHD",
    "respSign":"QIXWKSJHDQMMSDNJKQ",
    "channelType":"01"
}
```

##同步接口请求
请求信息：
参数|名称|值类型|是否可空|备注
---|:--:|---:|---:|---:|
channel|渠道|string|否|渠道会提前分配
version|版本号|string|否|当前版本为v1
data|数据区json|string|否|加密后的数据信息
sign|签名|string|否|用来验签
channelType|渠道类型|string|否|固定传递 01

例子：

```
{
    "channel":"xxxx",
    "version":"v1",
    "data":"KSLJDLQOWIEOAKSDKASDNJKANSDJNKASNJDKHSAKHDKASHDKJASKDHKASHDKHJAKHDAKJSDLSAJLDJALSJDLJSALJDLSDJSJDLKJ",
    "sign":"QIXWKSJHDQMMSDNJKQ",
    "channelType":"01"
}
```


##同步接口响应
响应信息：
参数|名称|值类型|是否可空|备注
---|:--:|---:|---:|---:|
channel|渠道|string|否|渠道会提前分配
version|版本号|string|否|当前版本为v1
respData|数据区json|string|否|加密后的数据信息
respSign|签名|string|否|用来验签
channelType|渠道类型|string|否|固定传递 01

例子：

```
{
    "channel":"xxxx",
    "version":"v1",
    "method":"order.push",
    "respData":"KSLJDLQOWIEOAKSDKASDNJKANSDJNKASNJDKHSAKHDKASHDKJASKDHKASHDKHJAKHD",
    "respSign":"QIXWKSJHDQMMSDNJKQ",
    "channelType":"01"
}
```


##请求data、响应respData JSON结构
参数|名称|值类型|是否可空|备注
---|:--:|---:|---:|---:|
code|业务码|int|否|code信息 200为正常。其他均为非正常
message|提示消息|string|否|根据code返回相应信息
data|数据|object|否|根据接口不同，返回不同的数据信息。


```
{
    "code":200,
    "message":"成功",
    "data":{
    	"demo":"demo"
    }
}
```
