# Github-Actions builds OpenWrt for xiaomi_ax3600

使用p3terx的模板,openwrt仓库使用[boos4721/openwrt](https://github.com/Boos4721/openwrt),本地配置好`.config`文件,上传到主目录下

### 个人自用精简固件,5.10内核

**主题:**
- 仅bootstrap

**服务:**
- adguardhome
- smartdns
- mosdns
- openclash
- store
- upnp

**问题:**

adguardhome有问题,adguardhmoe启用后,未运行未重定向

>**luci插件说明**,https://www.right.com.cn/forum/thread-344825-1-2.html
