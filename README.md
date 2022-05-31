# Parantric Lim`s CFW Configuration

------

![b63596ca-e19e-4998-aab1-1f86631ef8a4](https://raw.githubusercontent.com/Parantric/picture-bed/main/202205311807118.jpg)

------

> 基于本地 Subconvert 订阅地址转换应用程序，CFW 订阅地址自用转换

#### 调用模板

```
http://127.0.0.1:25500/sub?target=Clash&url=%URL%&config=%CONFIG%
```

其中：

- `URL` : 表示订阅地址（需要经过 [URLEncode](https://www.urlencoder.org/) 处理）
- `CONFIG`: 表示外部配置地址（需要经过 [URLEncode](https://www.urlencoder.org/) 处理）
