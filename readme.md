🚧 **Under Construction / 持续更新** 🚧

![GitHub last commit](https://img.shields.io/github/last-commit/soulteary/Home-Network-Note.svg?label=Last%20Update&style=flat-square)

![GitHub](https://img.shields.io/github/license/soulteary/Home-Network-Note.svg?style=flat-square)

**这几年积累/分享了不少实践内容，是时候把这个项目的坑填上了。**

## 项目说明

```text
记录搭建家用兼顾学习和娱乐网络环境的一些事情，以及折腾过的一些硬件的小经验。
```

## 主要需求

| 功能 |备份数据|数据交换|无线接入|数据同步|workflow|开发学习|游戏娱乐|
| --- | --- | --- | --- | --- | --- | --- | --- |
| **核心** | 安全 | 高速 | 安全 | 无感知 | 易定制 | 流畅 | 流畅 |
| **重要** | 高效 | 易用 | 简单 | 准确| 省心 | 省心 | 舒适 |
| **可选** | 易用 | 安全 | 快速 | 全平台 | - | 冗余保障 | - |

## 操作手册

<table>
<thead><tr>
<th>备份数据</th>
<th>数据交换</th>
<th>无线接入</th>
<th>数据同步</th>
<th>workflow</th>
<th>开发学习</th>
<th>游戏娱乐</th>
</tr></thead>
<tbody>

<tr>
<td>
<a href="./handbook-backup/strategy.md">数据备份策略</a>
</td>
<td>
<a href="./handbook-exchange/high-speed-data-exchange.md">高速数据交换</a>
</td>
<td>
<a href="./handbook-network-access/secure-network-access.md">安全的网络接入</a>
</td>
<td>
<a href="./handbook-syncing/data-exchange.md">免维护的数据同步</a>
</td>
<td>
</td>
<td>
<a href="./handbook-cicd/cicd.md">持续集成</a>
</td>
<td>
<a href="./enjoy-game.md">玩游戏的一些观点</a>
</td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>
<a href="./notes/gitlab-usage.md">如何使用 GitLab</a>
</td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>
<a href="./notes/docker-and-vmware.md">虚拟化和容器</a>
</td>
<td></td>
</tr>
</tbody>
</table>




### 额外要求

- 方案及方案中的配置尽可能**简单**。确保服务能够在运行一年以上后，对软硬件进行轻松简单的“维护、升级、替换”操作。
  - 目前方案从 2016 年使用至今，非常稳定，几乎没有变化。
- 网络中存在 20~50 台甚至以上设备在线时，网络需要依旧通畅。

### 场景举例

- [1] 家庭中的手机、平板、电脑均能够迅速完成数据自动同步、快速完成照片备份等操作。
- [2] 能够支持电脑数据每日自动备份，针对代码、文档进行额外备份。
- [3] 能够提供稳定网络，以支持日常观看在线视频、进行低延迟的在线游戏、实验性质的数据抓取、分析。
- [4] 能够支持数十台设备长时间联网，无须针对路由器相关网络设备或联网电子设备、智能设备、虚拟机进行额外的操作，包括并不仅限于重启、复杂脚本监控。
- [5] 设备均处于相对安全的网络环境中。

## 历史设备列表

```text
如果你考虑入手一些设备(主机/路由/网卡/显示器/储存/移动设备/娱乐/...)，或许可以从这里得到一些参考信息。
也可以翻到文档底部，看看哪些设备（断电设备）不值得购买。
```

[待补全的设备清单](./device-list-history.md) | [显示器相关](./display-history.md)

## 当前屋内常保持联网设备清单及方案

![网络结构](./assets/img/network-2017.10.png)

- [家用10～20台在线设备可参考网络方案](./network.md)
- [无线网络的方案及性能数据](./wifi.md)
- [有线网络的方案及性能数据](./lan.md)

### 🌈 宽带资源

> 不敢想假如家里没有稳定的网络会怎样

| 资源类型 | 明细 | 备注 |
| --- | --- | --- |
| 北京联通 | 固网 1000M | 下行 900Mbps / 上行 40Mbps |
| 北京电信 | 5G | 主网络，用于日常上网、热点 |
| 北京联通 | 5G | 备份网络，用于补充信号覆盖 |

- [1] 如果没有特殊需求，建议简化不必要的多线宽带，避免策略路由带来的各种问题，以及避免使用使用软路由聚合不同类型宽带，带来后续维护上的麻烦。
- [2] 带宽不建议依赖任何提速软件，避免当软件不可用时，带宽质量严重受损，以及带来的额外维护“提速软件”运行环境带来的成本。
- [3] 个人体验原因，已停用移动电话卡，取消原本无线三网接入，将服务转移至电信，除特殊情况，偶尔开通网络做 5G 聚合外，不再使用该网络。


### ⭐️ 路由网关

> 影响网络质量的核心设备，负责部分网络安全事务，[历史设备见文档](./device-list-history.md#%E8%B7%AF%E7%94%B1%E7%BD%91%E5%85%B3)。

| 资源类型 | 明细 | 网络 | 储存 | 开始服务 |
| --- | --- | --- | --- | --- |
| 交换机 | NETGEAR GS116E ^1 | 千兆LAN x16 | - | 2017 |
| 路由器 | Xiaomi AIot AX 3600 ^2 | 2G Wi-Fi / 5G Wi-Fi（Wi-Fi6） / 千兆LAN | - | 2020 |
| 路由器 | Newifi D2 ^3 | 2G Wi-Fi / 5G Wi-Fi / 千兆LAN | 8G | 2018 |
| 路由器 | Xiaomi AC2100 ^4 | 5G WIFI / 千兆LAN | - | 2020 |
| 路由器 | Xiaomi Mini 青春版 ^5 | 2G Wi-Fi / 百兆LAN | - | 2016 |
| 路由器 | 施耐德旅行插座 ^6 | 2G WIFI / 百兆LAN | - | 2018 |

- [1] 八口千兆交换机，用于扩展主路由网络吞吐能力，带 Web 管理界面，带铁壳散热，最大功耗仅10w，目前感觉最超值的一个设备。
- [2] 扩展主路由的 AP 能力，提供屋内设备以 Wi-Fi 6 模式，进行高速无线接入。
- [3] 全千兆四口主路由（二级路由），拥有 512M 内存和铁壳散热的路由器，延续 Newifi 极高的性价比，一度使用两台相同规格的设备作为拨号路由器和二级路由。
- [4] 偶尔在开发调试时使用，用于替换之前使用的[小米路由器第一版](./devices/XiaoMi-Route-Mini.md)，相比较之下，固件修改复杂度稍高一些，但是胜在全千兆。
- [5] 功耗极低，小巧方便，适合旅游或者临时需要网络进行调试的场景，三方适配的固件功能强大，如果公司不限制使用自建路由作为调试环境，强烈建议入一台。
- [6] 此插座自带一个简易的热点 WiFi 功能，如果你需要插上设备就自动组网，可以使用上面的设备，如果你没有自动组网等需求，那么这个能让你上网的插座，用起来体验还不错，唯一槽点，插座本身发热比较严重，或许对网络稳定性/质量有一定影响。


### 💻 主机资源

> 提供运算能力的本地设备，[历史设备见文档](./device-list-history.md#%E7%AC%94%E7%94%B5)。

| 序号 | 资源类型 | 明细 | 网络 | 储存 | 开始服务 |
| --- | --- | --- | --- | --- | --- |
| 1 | 编码机器 | MacBook Pro 16 | 千兆LAN & 5G Wi-Fi | 32GBRAM / 2T  | 2019 |
| 2 | 资源机器 | ThinkBook 15 | 千兆LAN & 5G Wi-Fi | 40GBRAM / 2T  | 2021 |
| 3 | 便携机器 | ThinkPad L14 | 千兆LAN & 5G Wi-Fi | 64GBRAM / 1T  | 2021 |
| 4 | 公司机器 | MacBook Pro 16 | 千兆LAN / 5G Wi-Fi | 16GBRAM / 1T  | 2020 |
| 5 | 资源机器 | Nuc8i5BEH | 千兆LAN / 5G Wi-Fi | 64GBRAM / 2T  | 2021 |
| 6 | 网络设备 | Nuc7CJYH | 千兆LAN | 8GBRAM / 256GB | 2021 |
| 7 | 码字机器 | MacBook Pro m1 | 千兆LAN & 5G Wi-Fi | 8GBRAM / 512GB | 2021 |

- [1] 时隔多年，终于等到的键盘改良款，体验非常好（i9 2.4GHz），尤其是在做复杂性能测试的时候。
- [2] 无独显版本，搭载 7nm 5800U，性能彪悍，作为补充资源机器购置。
- [3] 无独显版本，仅 45w 峰值功耗，性能非常强，核心数也非常多，作为一台便携的“服务器”使用，用于拓展本地开发资源，提供一个冗余一些的资源跑测试服务，替换之前使用的 [HP EliteDesk G4 800](./devices/HP-EliteDesk-G4-800.md) 小型工作站。
- [4] 公司机器，配置为 i7 2.6GHz ，实测性能大概比 i9 款弱 20%～30%。
- [5] 入手原因见[这篇文章](https://soulteary.com/2021/01/31/nuc-notes-linux-system.html)。在随后不断添置和更新设备后，这台设备职能更新为软件测试资源，提供搭建各种开源软件分布式环境场景所使用的虚拟机环境，极大的降低了笔记本发热的程度。
- [6] 用来提供稳定的“回家网络”、个人公开 Wiki 资源，以及解决群晖跑容器，硬盘不会休眠的问题。
- [7] 13-inch, m1 吃螃蟹，性能非常强，逼近 i9 的设备。


### 🚚 储存资源

> 用来持久化保存资料（开始服务从作为存储角色开始计算），[历史设备见文档](./device-list-history.md#%E5%82%A8%E5%AD%98%E4%BB%8B%E8%B4%A8)。

| 资源类型 | 明细 | 网络 | 储存 | 开始服务 |
| --- | --- | --- | --- | --- |
| 主力备份 | Synology DS 920+ ^1 | 千兆LAN | 17TB (8TB Raid1 / 8TB SHR / 1TB SSD) + 0.5TB SSD Cache | 2020 |
| 资源冷备 | 硬盘若干 ^2 | - | - | 2016 / 2018 / 2020 |
| 长期备份 | Canon G3800 ^3 | 2G WIFI | -      | 2019 |
| 清理备份 | Deli 9920 碎纸机 ^4 | - | -      | 2017 |
| 电力保障 | APC BR550G ^5 | - | - | 2017/2019 |

- [1] 新品发布时入手的 DS920+ 四盘位机器，取代之前服役了许久的 [Synology DS 718+](./notes/2021-ds718-plus-hard-drive-replacement-record.md) 和定制的 [HP Gen8 MicroServer](./devices/HP-Gen8-MicroServer.md)。使用3组盘来区分对待不同场景的数据，针对临时下载数据，使用 SSD 进行数据落地，对于诸如软件资源等持久性存储的一般数据使用 SHR 模式的磁盘存储，而对于宝贵的照片数据则使用 Raid 1 进行储存，并搭配 SSD Cache 对重复查询的数据进行缓存。
- [2] TBD 说明文本。
- [3] 打印不失为一种相对稳定的持久化保存方案，之前坏掉过一台，迫于需求又买了一台，价格便宜，非常好用。
- [4] 干掉持久化的纸质存储，最靠谱的莫过于加密级别的粉碎了，尤其是相对隐私敏感的内容。
- [5] 在所有电源都带稳流稳压作用后，添加一台UPS可以进一步防止市电闪断带来的数据损坏或者写输出脏掉的问题。在第一块使用了两年后，更换了一块电池，继续战斗，产品质量靠谱。


### 📱 移动设备 & 🎮 游戏设备

> 强依赖无线进行交互的设备

| 资源类型 | 明细 | 网络 | 储存 | 开始服务 |
| --- | --- | --- | --- | --- |
| 游戏机 | Switch 续航 | 5G WIFI | 忽略 | 2020 |
| 游戏机 | Switch Lite | 5G WIFI | 忽略 | 2020 |
| 游戏机 | PS4 | 2G WIFI | 500G HDD | 2017 |
| 游戏机 | PS4 Pro | 2G WIFI | 500G SSD | 2017 |
| 游戏机 | Switch | 2G WIFI | 忽略 | 2017 |
| 爪机 | iPhone 11 Pro | 4G / 5G WIFI | 512G  | 2019 |
| 爪机 | Redmi K30 Pro | 4G / 5G WIFI | 128G  | 2019 |
| 爪机 | Redmi K20 Pro | 4G / 5G WIFI | 128G  | 2019 |
| 爪机 | iPhone SE | 4G / 5G WIFI | 64G  | 2017 |
| 爪机 | iP3GS ^1 | 2G / 2G WIFI | 忽略 | 2017 |
| 游戏机 | PSVx2 ^2 | 2G WIFI | 16G / 64G | 2015 / 2016 |
| 游戏机 | 3DSx2 ^3 | 2G WIFI | 64G / 64G | 2014 / 2016 |
| 平板 | iPad Air2 | 4G / 5G WIFI | 128G (改) | 2015 |
| 平板 | iPad Pro 12' ^4 | 5G WIFI | 256G | 2018 |

- [1] 年度最值手机，作为monitor使用，极低功耗，可以愉快跑脚本，已购两台。
- [2] 一正一破，好处是可以联机的游戏，可以大号带小号玩，另外可以做PS4手柄，玩不需要L2R2键的游戏还可以。
- [3] 游戏性比SONY强，联机赛高！
- [4] 体验真的棒，新系统后，可以作为苹果副屏幕。

### 🔮 智能设备

> 当下的所谓智能不过是可编程或者扩展了原有的使用者能力

| 资源类型 | 明细 | 网络 |备注 |
| --- | --- | --- | --- |
| 网络音箱  | 小米音箱 Pro ^1 | 2G WIFI | 2019年  |
| 空气净化器  | 小米净化器 Pro ^2 | 2G WIFI | 2019年  |
| 智能台灯  | 飞利浦台灯 ^3 | 2G WIFI | 2017年  |
| 网络插座  | 小米 xN ^4 | 2G WIFI | 2017年  |
| 网络网关  | 小米 x2 ^5 | 2G WIFI | 2017年  |
| 传感装置  | 小米 xN ^6 | 2G WIFI/ZigBee | 2017年  |
| 网络摄像头 | 水滴 x3 ^7 | 2G WIFI | 2015年、2016年、2017年、2018年 |
| 网络摄像头 | 小方等 x2 ^8 | 2G WIFI | 2018年 |

- [1] 音质还行，而且支持绑定QQ音乐，考虑入两台组全屋播放。
- [2] “手动档”挺好使，其他自动档位比较“弱鸡”，正常运行基本静音，总体点赞。
- [3] 用了一年多后偶然发现居然可以使用“米家”管理，支持联动音箱进行语音控制。
- [4] 小米开放局域网协议之后，把控客都换成了小米，支持编程这件事太好了。
- [5] 小米网关+空调插座，对于空间利用率很高，而且支持ZigBee/WiFi，还能网络调试。
- [6] 门磁可以避免出门老想着有没有关好门的问题，烟雾等传感器避免检查厨房，很省心。
- [7] 2015年从小米换到360就一直使用，目前使用还好，小问题是启动音有点惊悚，4台设备经常会有一台显示离线，我所在的小区，想稳定使用需要额外提供移动热点，目前考虑替换掉。
- [8] 小方支持自定义固件，折腾通过，计划对接群晖后替换所有360摄像头。
- 控客的插座APP不是很好用，尤其是不给SDK，无法定制开发，国内版本也不支持简单DIY（需要拆+编程器），故弃用。

### 💣 历史设备

> 断电的设备

[设备列表及原因](./past.md)

## 其他记录

- [NUC 折腾笔记 - Linux 系统篇](https://soulteary.com/2021/01/31/nuc-notes-linux-system.html)
- [NUC 折腾笔记 - 储存能力测试](https://soulteary.com/2021/02/02/nuc-notes-storage-ability-test.html)
- [博客中的折腾笔记](https://soulteary.com/subject/life/)
- [2016年上半年 自组x86软路由/迷你服务器的一些考虑](./notes/2016-think-about-x86-route.md)
- [2016年组建家用迷你服务器](./notes/2016-build-mini-home-server.md)
- [日志收集和查看](log.md) ^1
- [1] 待更新。
