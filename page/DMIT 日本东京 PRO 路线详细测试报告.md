# DMIT 日本东京 PRO 路线详细测试报告

今天我们针对 DMIT 的日本东京 PRO 路线进行了全面测试，该线路三网回程采用 CN2 GIA，部分节点支持解锁 Netflix，目前官方正在排查和修复部分日本线路的问题。本次测试同步分析了网络性能及多项解锁能力，方便大家参考实际使用体验。

👉 [【推荐收藏】2025年 DMIT 最新优惠活动整理汇总 - 每日更新可用优惠套餐](https://bit.ly/dmit_coupon)

以下是今天所使用测试机的基础配置：

plaintext
vCPU：1C [AMD EPYC 7402P]
RAM：2G
Disk：40G
Bandwidth：500G
Network Port：300Mbps Shared Port
1 ipv4 & 1 ipv6


---

## 基准性能测试

**Bench 综合性能测试详情：**

plaintext
-------------------- A Bench.sh Script By Teddysun -------------------
 Version            : v2023-10-15
 Usage              : wget -qO- bench.sh | bash
----------------------------------------------------------------------
 CPU Model          : AMD EPYC 7402P 24-Core Processor
 CPU Cores          : 1 @ 2794.750 MHz
 CPU Cache          : 512 KB
 AES-NI             : ✓ Enabled
 VM-x/AMD-V         : ✓ Enabled
 Total Disk         : 39.2 GB (8.4 GB Used)
 Total Mem          : 1.9 GB (320.3 MB Used)
 System uptime      : 102 days, 23 hours, 46 min
 Load average       : 0.12, 0.04, 0.01
 OS                 : Debian GNU/Linux 11
 Arch               : x86_64 (64 Bit)
 Kernel             : 5.10.0-24-amd64
 TCP CC             : bbr
 Virtualization     : KVM
 IPv4/IPv6          : ✓ Online / ✓ Online
 Organization       : AS906 DMIT Cloud Services
 Location           : Tokyo / JP
 Region             : Tokyo
----------------------------------------------------------------------
 I/O Speed (平均)  : 541.3 MB/s
 Speedtest.net      : 上传 312.99 Mbps / 下载 298.47 Mbps / 延迟 0.28 ms
 Los Angeles, US    : 上传 218.71 Mbps / 下载 301.50 Mbps / 延迟 238.55 ms
 Tokyo, JP          : 上传 310.35 Mbps / 下载 295.83 Mbps / 延迟 67.68 ms
----------------------------------------------------------------------


**Geekbench 5 单核与多核性能测试：**

plaintext
CPU型号: AMD EPYC 7402P 24-Core Processor
单核测试分数: 810
多核测试分数: 809
系统信息:
- 操作系统: Debian GNU/Linux 11 (bullseye)
- 内核: Linux 5.10.0-24-amd64 x86_64
- 内存大小: 1.92 GB


---

## 流媒体解锁能力测试

### IPv4 解锁情况：
- **Netflix:** 支持完整解锁（地区：日本）
- **Disney+:** 支持解锁（地区：日本）
- **YouTube Premium:** 支持（地区：日本）
- **Amazon Prime Video:** 支持（地区：日本）
- **Spotify 注册:** 不支持
- **ChatGPT:** 可正常访问

### IPv6 解锁情况：
- **Netflix:** 仅支持原创内容
- **Disney+:** 支持解锁（地区：日本）
- **YouTube Premium:** 支持（地区：日本）

---

## 网络路由追踪测试

以下是通过不同运营商（上海移动、上海联通、上海电信）的路由追踪测试结果：

### 上海移动回程：
plaintext
1   193.41.248.195   日本东京   DMIT.com      延迟: 0.35 ms
2   221.183.90.241   中国上海   chinamobile.com 移动   延迟: 134.75 ms
3   211.136.112.200  中国上海   浦东新区移动   延迟: 34.60 ms


### 上海联通回程：
plaintext
1   193.41.248.195   日本东京   DMIT.com      延迟: 0.32 ms
2   59.43.181.33     中国上海   chinatelecom.cn 电信 延迟: 232.23 ms
3   59.43.138.45     中国上海   chinatelecom.cn 电信 延迟: 32.95 ms


### 上海电信回程：
plaintext
1   193.41.248.195   日本东京   DMIT.com      延迟: 4.72 ms
2   124.74.229.230   中国上海   电信          延迟: 32.95 ms


---

## 三网国内测速结果

plaintext
————————————————————————————————————————————————————————————————————
测速服务器信息   ↑ 上传速度 (Mbps) ↓ 下载速度 (Mbps) ↕ 延迟 (ms)
————————————————————————————————————————————————————————————————————
电信|江苏南京5G    ↑ 273.0 ↓ 191.7 ↕ 35.0
电信|天津5G        ↑ 248.3 ↓ 24.9 ↕ 52.6
移动|浙江杭州5G    ↑ 260.5 ↓ 33.9 ↕ 37.0
移动|陕西西安5G    ↑ 256.2 ↓ 289.0 ↕ 58.6
电信|四川成都      ↑ 230.6 ↓ 113.1 ↕ 62.6
————————————————————————————————————————————————————————————————————


---

## 总结

从测试结果来看，DMIT 日本东京 PRO 路线的整体性能优异，在国内的三网回程均表现出较低的延迟和稳定的带宽表现，并且其流媒体解锁能力对大部分日服和流媒体平台非常友好，特别适合需要观看日本地区内容的用户。此外，CPU 与 I/O 性能也足以支持绝大多数轻量级任务或搭建个人服务环境。如果你正在寻找一条高性价比的 VPS 路线，DMIT 确实值得考虑。