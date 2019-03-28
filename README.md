# 介绍
>该EFI可以使XPS 9570在Mojave环境下正常工作，这个配置的大部分内容是基于[Xigtun](https://github.com/Xigtun/xps-9570-mojave),[bavariancake](https://github.com/bavariancake/XPS9570-macOS)两位朋友的EFI借鉴得到的，同时807133286朋友向大家提供了非常及时的局部更新.在这里，我要对他们的无私帮助和奉献表示感谢。我总结了Xigtun和bavariancake的配置优缺点,内容如下：

## Xigtun 
 ### 优点
 * 解锁触控板的大部分高级手势
 * 支持触控屏幕
 * 亮度正常
 * 支持typec 转换成HDMI\DP输出
 ### 缺点
 * 睡眠唤醒黑屏
 * 无法驱动原生声卡
 * config过于冗余
 
## bavariancake
 ### 优点
 * 支持睡眠

 ### 缺点
 * 触控板不支持高级手势
 * 不支持屏幕触控
 * DSDT加载方法存在错误
 
## 我的改进
当然，以上配置已经可以让XPS 9570的几个版本正常使用，但离真正的fawlessly还是有差距。我致力于融合以上两位的工作成果，得到一个完善的配置。在`Mojave 10.14.3`版本下,我的配置解决了以下问题:

 * 支持Typc外接显示器输出
 * 支持睡眠与唤醒
 * 支持原生声卡驱动
 * 支持触控板手势与屏幕触控
 * 更少的DSDT加载错误
 * 利用CpuFriend注入Macbook pro 15.1的变频信息
 

# 硬件配置
 ## 已驱动
  * Machine :Dell XPS 9570
  * CPU: Intel i7-8750H
  * GPU: UHD630 + 
  * RAM: 16GB RAM
  * Display: 4K 夏普显示屏
  * SSD: PC401 NVMe SK hynix 512GB SSD
  * Audio: Realtek ALC298
  * Touchscreen
  * WLAN + Bluetooth : DW1830（已更换）
 ## 未驱动
  * Killer 1535 (无解)
  * Goodix fingerpint reader (无解)
  * Nvida Geforce 1050Ti (无解，已屏蔽)

# 软件环境
 * BIOS: 1.7.0,1.5.0
 * Mojave 10.14.3 + Windows 10 1809系统
 * macOS: 10.14.2, 10.14.3

# 使用方法
 * 将CLOVER放入EFI分区，使用config_install.plist进系统完成安装
 * 进入桌面后运行`sudo kextcache -i /`重建缓存
 * 用config.plist完成使能集显加速
 
 `config_10.14.4.plist`是我为了想升级10.14.4版本的朋友准备的，因为精力有限我还未能进行测试，期待有人反馈结果。

# 已知问题
 * 睡眠唤醒后，蓝牙随机出现不可用。
 * HDMI输出无效
 * USB定制未完成
# 待测试
 * 雷电三接口
 * 非4k、8750H的机型
 * 在10.14.4上运行

在我升级10.14.4失败之后，我停留在10.14.3（18D42）,在这个版本上机器工作得很好，希望有意愿的朋友可以尝试升级到10.14.3更高版本进行测试，期待更多的朋友可以加入进来，让XPS 9570 实现真正的Hackintosh!
