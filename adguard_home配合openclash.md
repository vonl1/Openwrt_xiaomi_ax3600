# adguard home 配合 openclash

## 思路:
adguard home设置使用53替换dnsmasq,接管路由器所有dns请求,通过adguard home过滤广告,上游设置为openclash监听的dns端口7874,

最终流量经过openclash完成国内,国外分流,实现科学上网的目的.

## 操作:

### adguard home
  - 53端口替换dnsmasq
  - web/设置/DNS设置/
    - 上游DNS设置为: 127.0.0.1:7874
    - 并行请求
    - Bootstrap DNS 服务器: 你家光猫上的DNS服务器
    - 点击 `应用` 保存
  - web/设置/常规设置
    - 日志配置/查询记录保留时间: 24小时 , 点击保存
    - 统计配置/统计保留: 7天 , 点击保存
  - web/过滤器/DNS 拦截列表
    - 添加阻止列表/从列表中选择/
      - AdGuard DNS filter
      - CHN: anti-AD
      - 上边两条基本够用,觉得不够自己网上找往里边添加
  - adguard home 设置完毕

### openclash/全局设置
  - 模式设置
    - redir-host 三种模式都可以
    - 勾选 仅代理命中规则流量
    - 勾选 仅允许常用端口流量
    - 勾选 实验性：绕过中国大陆 IP
  - DNS设置
    - 不勾选 本地 DNS 劫持
    - 勾选 自定义上游 DNS 服务器
    - 不勾选 追加上游DNS
    - 勾选 禁止 Dnsmasq 缓存 DNS
    - 设置自定义上游 DNS 服务器
      - 仅启用以下三条
      - nameserver 114.114.114.114 udp
      - nameserver dns.cloudflare.com/dns-query https
      - nameserver dns.google/dns-query https
  - 点击最下边的 应用配置 ,openclash设置完毕

## 检查

在openclash和adguard home都按照上边设置并启用后,检查一下 `openwrt` `网络` 下的 `DHCP/DNS`

`基本设置` 的 `DNS转发` 是否为空,不为空则删除,然后点击最下边的`保存&应用`

`高级设置` 的 `DNS服务器端口` ,如果端口是1745,删除掉1745,然后点击最下边的`保存&应用`

## 总结

openclash不要选fake-ip模式,因为你ping网站,它返回的是一个内网ip,不是网站的真实ip

openclash自定义dns服务器,多dns可能会出现dns污染,导致在浏览器中无法打开github

openwrt/服务/adguard home界面中的 `升级用的下载链接` ,里边默认是三个,仅保留一个`https://static.adguard.com/adguardhome/beta/AdGuardHome_linux_${Arch}.tar.gz`就行了
