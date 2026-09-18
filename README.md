# Open-Box MT3600BE 独立插件

这是给 GL.iNet MT3600BE/Beryl 7、ImmortalWrt 25.12 ARM64 使用的独立安装插件。

它**不编译进固件**，需要时手动安装；会下载官方 Open-Box ARM64 发布包并校验 SHA256，然后安装 LuCI 页面、sing-box、Node 和 Geo 数据。

## 安装

```sh
curl -fsSL https://raw.githubusercontent.com/yonggangdong56-stack/openbox-mt3600be-plugin/master/openbox-mt3600be.run | sh
```

建议先挂载 USB 固态硬盘。安装包约 97MB，安装后需要至少约 512MB 可用空间。

安装后访问：`http://路由器IP:2026`

Open-Box 与 OpenClash 可以共存，但不要同时开启透明代理、DNS 劫持或 TUN；使用前选择一个作为主代理。

卸载：

```sh
sh /opt/open-box/openwrt/initd/openbox-panel stop 2>/dev/null || true
sh /opt/open-box/openwrt/initd/openbox stop 2>/dev/null || true
rm -f /etc/init.d/openbox /etc/init.d/openbox-panel
rm -rf /opt/open-box
```
