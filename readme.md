## **CTP开放平台（Powered by TTS - Tick Trading System）**

Github集 1000 Star，[知乎krenx](https://www.zhihu.com/people/krenx)集 10000 收藏，将开启平台各接口源码开放进程。

开放平台采用与CTPAPI完全兼容的接口，一定程度上可替代simnow等模拟平台进行功能测试。 CTP程序无需修改代码也无需重新编译，只需在这里**下载与CTP API版本号一致的交易dll**，覆盖掉自己的即可，**行情dll不用改**，行情的接入地址可使用各期货公司的实盘地址。

提供CTPAPI 6.3.15、6.3.19、6.5.1、6.6.1全部在用的版本，对应支持win32、win64、linux、MacOS等多个操作系统。

![ctp开放平台全景图](https://user-images.githubusercontent.com/83346523/148639077-6c328032-b75a-4979-be8d-157de60cf3b4.jpg)

### 目录结构：
- 6.3.15_20190220 ~ 6.6.1_P1_20210406：开放平台标准模拟环境TTS系统的CTPAPI兼容接口，替换CTP官方动态库即可连接TTS系统。
- ctp2IB盈透：盈透证券的CTPAPI兼容接口。
- ctp2OST东方证券：东方证券的CTPAPI兼容接口。
- ctp2中泰证券XTP：中泰证券XTP柜台的CTPAPI兼容接口。
- ctp2华鑫证券STP：华鑫证券奇点柜台的CTPAPI兼容接口。
- ctp2QQ行情：腾讯行情的CTPAPI兼容接口。
- ctp2Sina行情：新浪行情的CTPAPI兼容接口。
- demo：CTPAPI开发相关的demo及工具源码。
- tools：生产力工具。
- docs：开发文档及行业资料。

### 各套环境运行状态监控：
- 监控页面地址：http://122.51.136.165:50080/detail.html
- 使用的技术：https://github.com/krenx1983/openctp/tree/master/tools/Ping
- 相关源码：https://github.com/krenx1983/openctp/tree/master/demo/ctpping

![613dc093f916d1bf0764e5365f202ff](https://user-images.githubusercontent.com/83346523/148802378-2c9b3d3f-1959-4aab-851a-cf55666806d8.png)
### **支持品种：**
- A股股票、债券、基金
- 上期所等国内全品种期货、期权
- 港股、美股（7x24环境已提供AAPL（苹果）、00700（腾讯）两个合约模拟交易）
- CME等外盘期货品种（即将上线）

### 相对Simnow优点：
- 支持负价交易（负价合约的合约号为MINUS，仅在7x24环境提供）。
- 支持部分撮合（支持部分撮合的合约号为TEST、BTC、MINUS），仅在7x24环境提供。
- 提供各交易所全商品模拟交易。
- 关注“CTP开放平台”公众号即可自动得到一个模拟号，回复注册可再注册多个模拟号，且即时在两套环境同时生效。
- QQ群546977604有问必答，解答CTP及各交易相关问题。
- 真正的7x24，1秒钟都不停。
- 除国内期货及期权外，还提供A股股票、债券、基金及港美股、外盘期货等全球市场模拟交易。
- 支持市价单。

### 知乎热门文章：
- [CTP开放平台（Powered by TTS - Tick Trading System）](https://zhuanlan.zhihu.com/p/425679896)
- [如何使用CTP开放平台提供的各项能力](https://zhuanlan.zhihu.com/p/451403422)
- [连接CTP开放平台报错4097的解决方法](https://zhuanlan.zhihu.com/p/453332727)
- [发布一批CTP链路检测工具](https://zhuanlan.zhihu.com/p/447148174)
- [发布一批行情显示工具（命令行版）](https://zhuanlan.zhihu.com/p/446972353)
- [CTP开放平台支撑系统（TTS）架构](https://zhuanlan.zhihu.com/p/367326886)
- [期货交易系统架构演变](https://zhuanlan.zhihu.com/p/360872258)
- [内存数据库交易系统架构第一篇--概览篇](https://zhuanlan.zhihu.com/p/382019469)
- [内存数据库交易系统架构第二篇--数据恢复机制](https://zhuanlan.zhihu.com/p/399605670)
- [交易系统的“白”（一）](https://zhuanlan.zhihu.com/p/430975046)

### 撮合方式（同时支持做市与撮合）：
- 撮合：完全由用户之间撮合，按价格优先、时间优先撮合成交。撮合模式的合约只有三个，合约代码分别为TEST、BTC、MINUS，其它合约均为做市模式。
- 做市：Simnow用的就是做市模式，以实盘行情盘口做市成交，即高于叫卖价的多单立即成交，低于叫买价的空单立即成交，否则挂在队列中等行情符合条件的时候成交。

### **开放平台仿真环境（交易时段与实盘一致）：**
- 交易前置 - tcp://121.36.146.182:20002
- 行情前置 - tcp://121.36.146.182:20004（建议直接使用CTP实盘行情前置，行情前置均不校验密码）

### **开放平台7x24环境（不间断轮播某天行情）：**
- 交易前置 - tcp://122.51.136.165:20002
- 行情前置 - tcp://122.51.136.165:20004

### **CTP实盘行情前置地址：** （随便找的几个实盘地址，自己可以替换成其它的，行情前置都是不校验密码的，用户名也可以为空）
- tcp://180.169.112.54:42213
- tcp://140.207.168.9:42213
- tcp://180.168.212.75:41313
- tcp://27.115.78.155:41313
- tcp://180.168.102.233:41168
- tcp://112.64.143.220:41168

### **模拟账号：** 
扫扫下面的二维码，关注开放平台公众号，即可获得一个模拟账号，也可以回复"注册"再申请新的模拟号，一个微信号最多可以申请3个模拟账号，可以回复"查询"得到已注册的模拟账号列表。注册的模拟账号都可以在以上两个环境使用，两套环境独立结算，但是账号相同。

![qrcode_for_gh_564e4bf4668c_258](https://user-images.githubusercontent.com/83346523/120095274-ad600a00-c157-11eb-8496-7d680bd1f39b.jpg)

### **CTP程序接入股票柜台：**
除提供开放平台模拟交易外，还提供使用CTP接口接入证券柜台的能力，可以进行股票、债券、逆回购、新股申购、融资融券、ETF期权等交易，同样使用CTP接口将证券柜台接口封装成跟CTP完全兼容的动态库，使得CTP程序无需任何修改，只更换CTP动态库即可接入证券柜台，目前已完成华鑫证券、中泰证券股票交易接入功能，同样发布了目前在用的四个CTPAPI版本，分别提供win32、win64、linux三套动态库。

股票接入方式采用**直连证券柜台**方式，不经过开放平台处理，因此需要向证券公司申请模拟账号。
- **华鑫证券**，N视界模拟平台QQ客服群：860160807，加群验证信息填openctp（否则可能通过不了），模拟账号申请地址：http://www.n-sight.com.cn
- **中泰证券**，XTP柜台QQ客服群：188500929，加群验证信息填openctp（否则可能通过不了），模拟账号申请地址：https://xtp.zts.com.cn


### **已官方支持TTS通道（CTP开放平台）的产品：**
- [vn.py（知名Python量化交易客户端，支持全球市场交易）](https://www.vnpy.com/)
<img src="https://user-images.githubusercontent.com/83346523/136988918-1159fc88-073e-4b6f-a8d6-3f33991e8a72.png" alt="vnpy" width="700" height="400" />

- [MT5CTP（MT5软件，已支持国内A股、期货及期权交易）](https://www.zhihu.com/people/mt5ctp)
<img src="https://user-images.githubusercontent.com/83346523/136989596-b12d91e8-48a0-4b26-bcaf-fdfca52d962c.png" alt="mt5ctp" width="700" height="400" />

- [TextTrader（CTP开源命令行交易终端，支持A股、期货及期权交易）](https://github.com/krenx1983/TextTrader)
<img src="https://user-images.githubusercontent.com/83346523/136989754-1f0130e6-5d75-427f-bbf3-7ed084b6eae1.png" alt="texttrader" width="700" height="400" />

### **通过自己替换dll可接入TTS通道（CTP开放平台）的产品：**
- [快期V3（CTP期货交易客户端）](https://zhuanlan.zhihu.com/p/376482285)
<img src="https://user-images.githubusercontent.com/83346523/138928402-f7e12a28-50d3-457b-9c0a-32b356448913.png" alt="快期V3" width="700" height="400" />
- [快期V2（CTP期货交易客户端）](https://zhuanlan.zhihu.com/p/432252376)
<img src="https://user-images.githubusercontent.com/83346523/148678947-b2a7ed9c-f77f-43d6-8e85-74b2c9ca4c44.png" alt="快期V2" width="700" height="400" />
- [TBTerminalCTP（交易开拓者）](https://zhuanlan.zhihu.com/p/437818698)
<img src="https://user-images.githubusercontent.com/83346523/149624377-01c97148-9e34-4f2b-8bb3-c43b57340284.png" alt="TBTerminal" width="700" height="400" />

### **QQ交流群：564385877**

<img src="https://user-images.githubusercontent.com/83346523/146651068-3c2b3401-8c87-4ff3-beb4-a86492ea6bef.png" alt="QQ群二维码" width="300" height="300" />

### **特别说明：**

AuthCode、AppID认证信息任意填，不作校验

Broker任意填，填什么就回什么

<u>虽然也可以从平台接收实时行情，但是不建议这么做，除非玩TEST等自建合约，否则建议直接使用CTP数据源。从平台接收行情，同交易一样需要更换行情dll。</u>


<u>*本模拟平台不对模拟结果作任何保证，依据本平台测试结果进行实盘交易的后果完全由使用者自己承担。*</u>
