# 24.8 月底将更新最最关键的教程……

# Cloudflare-workers/pages 代理脚本

### 本项目仅支持本地化部署，不依赖订阅器、节点转换等第三方外链引用，无需担心节点订阅被盗查

---

## 脚本特色：

### 懒人小白专用！默认节点都为 CF 官方 IP，无需频繁更新订阅获取客户端优选 IP

#### Workers 方式：支持 vless+ws+tls、trojan+ws+tls、vless+ws、trojan+ws 代理节点

#### Pages 方式：支持 vless+ws+tls、trojan+ws+tls 代理节点

#### CF Vless/Trojan 的单节点支持 path 路径自定义三类 proxyip（IPV4 形式、IPV6 形式、域名形式）

#### 支持单节点链接、聚合通用节点订阅、sing-box 节点订阅、clash 节点订阅

---

## 一：CF Vless 节点可自定义内容

#### 方式一（推荐）：可修改 Vless_workers_pages 文件下的\_worker.js 文件

1、UUID 必须自定义（第 7 行）

2、如果无法访问 CF 类网站或者 ChatGPT 网页版，说明 ProxyIP 失效，可更换 ProxyIP，自定义（第 9 行）

3、订阅节点的优选 IP（第 13-27 行）与端口（第 30-44 行），优选 IP 与端口两者变量编号须对应

4、伪装网页默认留空，显示为本地 IP 信息代码界面，可自定义（第 10 行），为避免风险建议默认留空

#### 方式二：也可在 CF-workers/pages 界面中使用变量设置

注：变量设置结果将覆盖本地修改结果
| 变量作用 | 变量名称| 变量值要求| 变量默认值|
| :--- | :--- | :--- | :--- |
| 1、必要的 uuid | uuid |符合 uuid 规定格式 |万人骑 uuid：77a571fb-4fd2-4b37-8596-1b7d9728bb5c|
| 2、能上 CF 类网站 | proxyip |ipv4 地址、域名、[ipv6 地址]|proxyip 域名：代码第 9 行|
| 3、订阅节点优选 IP | ip1 到 ip13 |CF 官方 IP、CF 反代 IP、CF 优选域名| CF 官方不同地区的 visa 域名|
| 4、优选 IP 对应端口 | pt1 到 pt13 |CF13 个标准端口、反代 IP 对应任意端口| CF13 个标准端口|

---

## 二：CF Trojan 节点可自定义内容

#### 方式一（推荐）：可修改 Trojan_workers_pages 文件下的\_worker.js 文件

1、密码必须自定义（第 4 行）

2、如果无法访问 CF 类网站或者 ChatGPT 网页版，说明 ProxyIP 失效，可更换 ProxyIP，自定义（第 5 行）

3、订阅节点的优选 IP（第 9-23 行）与端口（第 26-40 行），优选 IP 与端口两者变量编号须对应

4、伪装网页默认留空，显示为本地 IP 信息代码界面，可自定义（第 6 行），为避免风险建议默认留空

#### 方式二：也可在 CF-workers/pages 界面中使用变量设置

注：变量设置结果将覆盖本地修改结果，每更新变量需要重新上传一次原始 pages 文件
| 变量作用 | 变量名称| 变量值要求| 变量默认值|
| :--- | :--- | :--- | :--- |
| 1、必要的密码 | pswd |任意字符号 |万人骑密码：trojan|
| 2、能上 CF 类网站 | proxyip |ipv4 地址、域名、[ipv6 地址]|proxyip 域名：代码第 5 行|
| 3、订阅节点优选 IP | ip1 到 ip13 |CF 官方 IP、CF 反代 IP、CF 优选域名| CF 官方不同地区的 visa 域名|
| 4、优选 IP 对应端口 | pt1 到 pt13 |CF13 个标准端口、反代 IP 对应任意端口| CF13 个标准端口|

---

## 三：CF Vless/trojan 的单节点支持 path 路径自定义 proxyip

支持 IPV4、IPV6(需中括号)、域名三种方式

可在客户端上的 path 设置处直接修改：/pyip=IPV4 地址 ； /pyip=[IPV6 地址] ； /pyip=域名

注意：仅影响当前客户端正在设置的单节点，并不影响其他单节点或者订阅节点的 proxyip

---

## 四：查看配置信息与分享链接

CF Vless：在网页地址栏输入 https:// workers 域名 或者 pages 域名 或者 自定义域名 /自定义 uuid

CF Trojan：在网页地址栏输入 https:// workers 域名 或者 pages 域名 或者 自定义域名 /自定义密码

注意：使用自定域时，原先 workers 域名 或者 pages 域名下的配置信息与分享链接依旧可用

---

## 五：优选 IP 应用

如果你没有天天最高速度或者选择国家的需求，使用默认的 CF 官方不同地区的 visa 域名即可（IP 落地地区都为美国）

推荐好记的懒人专属 CF 官方 IP 如下（IP 落地地区都为美国，支持 13 个标准端口切换），称之为"冲在最前的不死 IP"

104.16.0.0

104.17.0.0

104.18.0.0

104.19.0.0

104.20.0.0

104.21.0.0

104.22.0.0

104.24.0.0

104.25.0.0

104.26.0.0

104.27.0.0

172.66.0.0

172.67.0.0

162.159.0.0

2606:4700:: 需 IPV6 环境

通过配置变量修改，可使用他人分享的 IP 或者域名，也可以自行本地优选，相关优选应用与脚本可参考视频教程

注意：多个 CF 节点在客户端使用负载均衡或者自动选择时，建议所有应用的节点都为同一个国家地区，以避免不同国家之间的 IP 乱跳现象

---

## 客户端推荐

#### 启用分片(Fragment)功能的好处：无视域名被墙 TLS 阻断，从而让 workers 等被墙的域名支持 TLS 节点

#### 提示：未被墙 TLS 阻断的自定义域名或 pages 域名无需开启分片就可使用 TLS 节点

目前支持该功能的平台客户端如下 (更新中……)

1、安卓 Android：[v2rayNG](https://github.com/2dust/v2rayNG/tags)、[Nekobox](https://github.com/maskedeken/NekoBoxForAndroid/tags)、[Karing](https://github.com/KaringX/karing/tags)、v2box

2、电脑 Windows：[v2rayN](https://github.com/2dust/v2rayN/tags)、[Hiddify](https://github.com/hiddify/hiddify-next/tags)、[Karing](https://github.com/KaringX/karing/tags)

3、苹果 Ios：Karing、Shadowrocket(小火箭)、Streisand、v2box

4、软路由 Openwrt：[homeproxy](https://github.com/kiddin9/openwrt-packages)

注意：其他平台客户端未开启分片功能情况下，workers 域的 6 个 443 系 TLS 节点是不可用的

注意：Shadowrocket(小火箭)、v2box、v2rayn、v2rayng 客户端对 trojan+ws 有强制开启 TLS 问题，造成 trojan+ws 不通。且 clash 订阅没有 trojan+ws 节点。特此说明

---

### 相关说明及注意点请查看[甬哥博客](https://ygkkk.blogspot.com/2023/07/cfworkers-vless.html)

### 视频教程：

[CF workers 永久免费 vless 节点搭建教程（一）：全网首发演示跳 IP 现象，解密两大节点使用技巧，优选 IP、优选域名的优缺点说明](https://youtu.be/9V9CQxmfwoA)

[CF workers 永久免费 vless 节点搭建教程（二）：优选反代 IP 一键脚本发布，pages 部署教程，多平台客户端设置说明，独家探讨 CF 免费代理敏感安全问题](https://youtu.be/McdRoLZeTqg)

[CF workers 永久免费 Trojan 节点搭建教程（三）：无需自定义域名，workers 与 pages 两方案部署优选 IP 节点；CF Trojan 与 CF Vless 对比总结；如何看待 Trojan 被识别](https://youtu.be/lmhhL8M1k0I)

强烈推荐：[CF vless/trojan 永久免费节点教程（四）：解读优选官方 IP、优选反代 IP、优选域名三者的关系与特点；ProxyIP 存在的意义](https://youtu.be/NaLd-orwFUE)

强烈推荐：[CF vless/trojan 永久免费节点教程（五）：不用自定义域名？不用频繁优选 IP？不用订阅器？总结 CF 节点与域名的结构关系图](https://youtu.be/8s-ELRuFaeE)

最新推荐：[CF vless/trojan 永久免费节点教程（六）：节点不能用，问题出在哪？多平台免费客户端设置指南及避坑说明](https://youtu.be/8E0l0nQWLxs)

[直播精选回顾：CF workers vless 免费节点四大特点，节点被断流阻断问题](https://youtu.be/9OHGpWlfdJ0)

[ClouDNS 永久免费域名最终教程：CF pages vless 自定义域名直接部署](https://youtu.be/PN0BLANXh4I)

---

---

---

---

## 优选域名、优选官方 IP+反代 IP 一键脚本（在本地网络环境下利用 termux 或者 ish 运行）：

### CF-CDN 优选公共大厂域名脚本，苹果安卓手机平板专用：

```
curl -sSL https://gitlab.com/rwkgyg/CFwarp/raw/main/point/CFcdnym.sh -o CFcdnym.sh && chmod +x CFcdnym.sh && bash CFcdnym.sh
```

---

### CF-优选官方 IP+反代 IP 二合一脚本，苹果安卓手机平板专用：

```
curl -sSL https://gitlab.com/rwkgyg/CFwarp/raw/main/point/cfip.sh -o cfip.sh && chmod +x cfip.sh && bash cfip.sh
```

---

### 交流平台：[我的博客地址](https://viptv.work)、[我的 YouTube 频道](https://www.youtube.com/@HeFung)、[甬哥 TG 电报群组](https://t.me/viptv_work_group)、[甬哥 TG 电报频道](https://t.me/viptv_work)

### 代码来源：[yonggekkk](https://github.com/yonggekkk/Cloudflare_vless_trojan)、[ca110us](https://github.com/ca110us/epeius)、[emn178](https://github.com/emn178/js-sha256/blob/master/src/sha256.js)、[3Kmfi6HP](https://github.com/3Kmfi6HP/EDtunnel)、[badafans](https://github.com/badafans/Cloudflare-IP-SpeedTest)、[XIU2](https://github.com/XIU2/CloudflareSpeedTest)

### 声明：所有代码来源于 Github 社区，并通过 ChatGPT 进行整合
