![license](https://img.shields.io/github/license/roacn/Actions-OpenWrt-Lede-N1?color=ff69b4)
![N1_plus](https://github.com/roacn/Actions-OpenWrt-Lede-N1/actions/workflows/single_plus.yml/badge.svg)
![N1_mini](https://github.com/roacn/Actions-OpenWrt-Lede-N1/actions/workflows/single_mini.yml/badge.svg)
![Build lede](https://github.com/roacn/Actions-OpenWrt-Lede-N1/actions/workflows/N1_Multi.yml/badge.svg)
![code-size](https://img.shields.io/github/languages/code-size/roacn/Actions-OpenWrt-Lede-N1?color=blueviolet)


 ![applist](https://github.com/roacn/N1Openwrt/blob/master/imgs/N1-OpenWrt.jpg?raw=true)

# 源码来源：

[![Lean](https://img.shields.io/badge/source-Lean-red.svg?style=flat&logo=appveyor)](https://github.com/coolsnowwolf/lede) 
[![ophub](https://img.shields.io/badge/kernel-ophub-orange.svg?style=flat&logo=appveyor)](https://github.com/ophub/amlogic-s9xxx-openwrt) 
[![unifreq](https://img.shields.io/badge/package-unifreq-yellow.svg?style=flat&logo=appveyor)](https://github.com/unifreq/openwrt_packit) 
[![P3TERX](https://img.shields.io/badge/actions-P3TERX-success.svg?style=flat&logo=appveyor)](https://github.com/P3TERX/Actions-OpenWrt)
[![mingxiaoyu](https://img.shields.io/badge/actions-mingxiaoyu-blue.svg?style=flat&logo=appveyor)](https://github.com/mingxiaoyu)
[![helloworld](https://img.shields.io/badge/helloworld-fw876-blueviolet.svg?style=flat&logo=appveyor)](https://github.com/fw876/helloworld)
[![app](https://img.shields.io/badge/app-kenzok8-violet.svg?style=flat&logo=appveyor)](https://github.com/kenzok8)



# 如何使用
1. fork项目
2. 在secrets中创建RELEASES_TOKEN，一般一次编译要2~4小时，所以要创建一个github发布用的token。
3. 点击Actions -> Workflows -> Run workflow -> Run workflow 
4. N1 Multiple Version 多版本编译
5. N1 Single Version 只编译一个版本
6. Update Checker, 上游更新则编译。MULTIPLE_BUILD: true **编译mini和plus多版本编译**  false，**只编译mini**

------

## 用户名和密码
 * User: root
 * Password: password
 * Default IP: 192.168.1.2
------
## 防火墙
默认自定义防火墙: iptables -t nat -I POSTROUTING -o eth0 -j MASQUERADE

## app list:（mini 图不代表最新的）
 * jd-dailybonus
 * passwall
 * ssr+
 * ServerChan
 * aria2
 * ddns
 * samba4
 * KMS 
 * docker
 * zerotier
 * flowoffload
 
 ![applist](https://github.com/mingxiaoyu/N1Openwrt/blob/master/imgs/mini.jpg?raw=true)
 
 ------
 # N1 U盘写入刷emmc
```
cd      /root
./install-to-emmc.sh
```
如果一直卡在fdisk失败那里的解决办法：一是再多试几次，如果还不成功，则需要手动清空分区表然后再重试，具体命令:
```
  dd   if=/dev/zero   of=/dev/mmcblk2  bs=512  count=1  &&  sync
```

升级降级方法统一为：
把 update-amlogic-openwrt.sh 及 img镜像上传至  /mnt/mmcblk2p4
```
cd    /mnt/mmcblk2p4
chmod   755  update-amlogic-openwrt.sh
./update-amlogic-openwrt.sh    xxxxx.img
```

# 固件发布:

[![GitHub release (latest by date)](https://img.shields.io/github/v/release/roacn/Actions-OpenWrt-Lede-N1?style=for-the-badge&label=下载&&color=00aa66)](https://github.com/roacn/Actions-OpenWrt-Lede-N1/releases/latest)
------
 # 感激 
  * [mingxiaoyu](https://github.com/mingxiaoyu)
  * [P3TERX](https://github.com/P3TERX/Actions-OpenWrt)提供的脚本参考
 
 ## 云编译的规格
https://docs.github.com/en/actions/reference/virtual-environments-for-github-hosted-runners#supported-runners-and-hardware-resources

