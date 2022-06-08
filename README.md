# Parantric Lim`s CFW Configuration

![artwork_141203](F:\Syn_Cache\同步空间\download_cache\artwork_141203.jpg)

------

> 基于 **[老王订阅转换](https://sub.rxsmw.top/)**，CFW 订阅地址自用转换

####  :rocket: 远程调用模板

```
https://sub.rxsmw.top/sub?target=clash&new_name=true&url=%URL%&config=%CONFIG%
```

其中：

- `URL` : 表示订阅地址（需要经过 [URLEncode](https://www.urlencoder.org/) 处理）
- `CONFIG`: 表示外部配置地址（需要经过 [URLEncode](https://www.urlencoder.org/) 处理）

#### :loop: 方便查阅

##### 策略组

- url-test:延迟最低，每隔一段时间进行延迟测试，选择延迟最低的节点。
- fallback:故障转移，每次都选择组内的第一个节点，无法使用再更换另一个，以此类推。
- load-balance:负载均衡，每个节点都用用，但是由于很多机场都有连接数的设置限制，所以，实际很少用。
- select:手动选择，顾名思义。

##### 规则配置

- DOMAIN-SUFFIX:域名后缀匹配。
- DOMAIN:域名匹配。
- DOMAIN-KEYWORD:匹配域名关键字，更为模糊的规则。
- IP-CIDR:根据 ip 段进行分流。
- SRC-IP-CIDR:通过源 ip 所属的 ip 段进行分流。
- GEOIP:通过解析的 ip 所属地进行分流。
- DST-PORT:通过目标端口进行分流。
- SRC-PORT:通过源端口进行分流。
- MATCH:全匹配，一般放在最后用来捕捉漏网之鱼。

> **当有多个规则可以匹配时，将会匹配到最先出现的规则。即在文本中位于最前面的规则。**

##### ruleset

> 基本格式:ruleset=你想走的策略组或节点,rules/你的list.list
>
> **需要注意的是，根据出现先后顺序生成规则，因此如果你想让某个 list 有更高的优先级，在文件开头写它。**

##### custom_proxy_group

- custom_proxy_group=组名`类型`策略组1`策略组2`策略组3`
- custom_proxy_group=组名`类型`(正则)`测速url(如果需要的话)`测速周期(如果需要的话)

##### 正则表达式

> 几个常用的匹配节点正则公式，可以组合嵌套搭配使用。

- **(?!.*(A)).*(B)**：不包括A，但是包括B。
- **(A).*(B)**：既包含A也包含B。
- **(A)|(B)**：包含A或者B。
- **^((?!A).)*$.**：不包含A。
- **^(?!.*abc)**：不包含abc。

#### 参考

:bookmark: [**ImAubrey**](https://github.com/ImAubrey/ImAubrey)

:bookmark: [**老王订阅地址转化**](https://sub.rxsmw.top/)

:bookmark: [**参考 Clouder's Blog**](https://www.codein.icu/clashtutorial/)

:bookmark: [**正则表达式参考 GitHub 文档**](https://github.com/ziishaned/learn-regex/blob/master/translations/README-cn.md)

**:bookmark: [正则表达式在线测试工具](http://www.regexp.cn/Regex)**
