# Quantumult X 新手入门教程
电报交流群：https://t.me/kejifx <br>
Quantumult X 视频教程：https://youtu.be/oOFGDXMBD5s

## <a href="https://github.com/kjfx/QuantumultX/"><img width="40" src="https://github.com/kjfx/QuantumultX/blob/main/qx.png" /></a>  一、Quantumult X 简介与下载
Quantumult X 简称“圈X”，是一款功能强大的网络工具，本文主要介绍它的代理功能。<br>
Quantumult X 目前支持的协议： SS/SSR、V2Ray、Trojan、HTTP(S)<br>
Quantumult X 是一款付费APP，7.99美元，需要用美区等AppleID账号登录 Apple Store 下载。

注册美国AppleID教程：<a href="https://github.com/kjfx/AppleID" target="_blank">https://github.com/kjfx/AppleID</a><br><br>

## 二、Quantumult X 添加节点，订阅链接
#### 1、通过机场订阅链接导入
- Quantumult X 支持SS/SSR订阅链接、支持 Quantumult X 格式的 V2Ray和Trojan订阅链接。
- 机场网站有 Quantumult X 订阅链接的，直接复制订阅链接到 圈X的引用（订阅）里粘贴，或者点击导入到 Quantumult X 。
- 机场网站无 Quantumult X 订阅链接的，SS/SSR订阅链接可以使用，如果是V2Ray和Trojan订阅链接不能直接导入 Quantumult X ，<br>
需要添加一个 <code>资源解析器</code>，使用 <code>资源解析器</code> 后，可以将 Quantumult X 不识别的 节点或订阅链接 轻松的导入。
<span>
    
- :airplane: 如何添加资源解析器？<br>
打开Quantumult X 配置文件，找到 <code>[general]</code> 位置，添加以下代码：
</span>

    resource_parser_url=https://raw.githubusercontent.com/KOP-XIAO/QuantumultX/master/Scripts/resource-parser.js

#### 2、通过 URL 和 扫码 添加节点
Quantumult X 支持SS/SSR节点链接和扫码添加、支持 Quantumult X 格式的 V2Ray和Trojan节点链接和扫码添加，大部分机场的V2Ray和Trojan节点链接不能直接通过扫码添加。

#### 3、手动添加节点
<span>
    
- vmess节点格式
</span>

    vmess=example.com:443, method=chacha20-poly1305, password=pwd, obfs=wss, obfs-host=example.com, obfs-uri=/ws, tls13=true, fast-open=false, udp-relay=false, tag=节点名称

<span>
    
- Trojan节点格式
</span>

    trojan=example.com:443, password=pwd, over-tls=true, tls-host=example.com, tls-verification=true, tls13=true, fast-open=false, udp-relay=false, tag=节点名称


#### 4、订阅链接转换
- 地址1（将V2Ray订阅链接转成圈X订阅链接）：https://dove.589669.xyz/web
- 地址2（将vmess节点链接转成订阅链接）：https://bianyuan.xyz/

## <h2><a href="https://github.com/kjfx/QuantumultX/"><img width="40" src="https://github.com/kjfx/QuantumultX/blob/main/qx.png" /></a>  第二部分：Quantumult X 策略组和分流规则，添加使用教程</h2>

<h3>策略组</h3>

#### 1、策略组是什么？
- 策略组可以实现 自动切换节点、节点筛选、是否走代理等。
- 策略组 需要配合 分流规则 使用。
- 策略组 可包含多个节点和策略组。

#### 2、Quantumult X 自带 3 种策略。

- PROXY（代理）
- DIRECT（直连）
- REJECT（拒绝）

#### 3、Quantumult X 策略组类型
- static 静态策略-手动选择节点
- available 健康检查-自动选择节点，从第一个节点开始检查是否可用，直到选择可用节点。
- round-robin 负载均衡-轮询调度，轮流调用节点使用，IP可能会一直变。
- dest-hash
- url-latency-benchmark 自动测速-自动选择延迟低的节点

