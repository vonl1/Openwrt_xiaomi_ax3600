# 不建议使用release中的固件，时间太久了！
# 不建议使用release中的固件，时间太久了！
# 不建议使用release中的固件，时间太久了！

## 这个仓库不再更新，本人现在用的是lede闭源固件[onedrive下载链接：](https://1drv.ms/u/s!AgA0BIPkGX_L7DXPnaZCpnZ4XfZ5
### 不建议ax3600开adg+openclash，512mb的内存太小了，openclash现在日常占用大约60-80mb，adg大约30-40mb，很容易爆内存，我ax9000开这俩都要定时要重启，长时间使用dns有问题（很奇怪）
### lede的固件信号好一点，ax3600就放在老家给家里人用，什么插件都不开，稳定使用就行

# Github-Actions builds OpenWrt for xiaomi_ax3600

使用p3terx的模板,openwrt仓库使用[boos4721/openwrt](https://github.com/Boos4721/openwrt),本地配置好`.config`文件,上传到主目录下

## 个人自用精简固件,最新内核,不定期更新

# 推荐6-09版本，稳定使用一个多月，后续更新未测试

**网关地址:`10.10.10.1`**

**密码:`boos`**

**WIFI密码：1234567890**

### 主题:
- 仅bootstrap

### 服务:
- adguardhome
- openclash
- store
- upnp

### 介绍一下这个固件选择这些的原因

argon主题,openclash全局设置显示不全,弃掉,仅使用bootstrap

aliyunwebdav,store里边有,想用自己安装,弃掉

只留openclash和adguard home,因为这两个配合能过滤广告和科学上网;具体配置看点下边的链接去看

#### [adguard home 配合 openclash实现科学上网+广告过滤](https://github.com/vonl1/Openwrt_xiaomi_ax3600/blob/main/adguard_home%E9%85%8D%E5%90%88openclash.md)

>**luci插件说明**,https://www.right.com.cn/forum/thread-344825-1-2.html


### ax 9000 uboot 
ax 9000 uboot file 暗云的uboot，不推荐使用，会更改默认分区表，所有官方分区固件都刷不上去，只有大雕付费VIP群的闭源固件能用，很蛋疼
>https://www.right.com.cn/forum/thread-8275373-1-1.html
