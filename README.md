# CMCC-DNSMasq
##效果测试
* 139.196.59.110

##对移动网络作出的优化
1. 上游服务器为DNSPod Public DNS。
2. 将 Akamai CDN 解析到香港节点，可以加速 App Store 下载。（香港节点只有移动不绕路，所以，电信联通还是用 V2EX DNS 比较好）
3. 为 PSN, Xbox Live, 任天堂作出优化，加快更新、下载游戏以及更新系统的速度。同时还对EA、育碧、Origin、Steam、Rockstar 的服务器进行了优化。
4. 绕过移动自带的墙中墙（参见 /t/250906）
5. 将被污染的域名解析到正确的IP（如维基百科、EdgeCast CDN、Github Gist等）
6. 将不存在的网站解析到未被Block的IP（而且可以看油管的视频哦！）
7. V2EX没有移动节点，移动访问最快的节点实际上是香港节点，所以解析到了香港IP（因为去香港要经过GFW，所以请使用HTTPS）
8. 为部分有移动CDN的网站解析到移动CDN。
9. 将Dropbox等网站解析到反向代理。
10. 目前所有.tw的网站都会被解析到反向代理，原因你懂的。

##使用
1. 安装DNSMasq（如果已有可以跳过）
Debian, Ubuntu
        sudo apt-get install dnsmasq
RedHat. CentOS
        sudo yum install dnsmasq
2. 将```dnsmasq.conf```放入```/etc/dnsmasq.d/```
3. 重启DNSMasq
        service dnsmasq restart
