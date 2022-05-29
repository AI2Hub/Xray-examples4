## Xray + Shadowsocks-2022-TCP 手动安装教程

1.安装Xray

```
bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ install --version 1.5.6
```

2.下载配置文件

```
curl -Lo /usr/local/etc/xray/config.json https://raw.githubusercontent.com/chika0801/Xray-examples/main/Shadowsocks-2022-TCP/config_server.json
```

3.下载路由规则文件加强版

```
curl -Lo /usr/local/share/xray/geosite.dat https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geosite.dat && curl -Lo /usr/local/share/xray/geoip.dat https://github.com/Loyalsoldier/v2ray-rules-dat/releases/latest/download/geoip.dat
```

4.设置密钥
- 使用SSH客户端软件连接你的VPS，输入`openssl rand -base64 32`生成密钥。
- 使用WinSCP连接你的VPS，进入/usr/local/etc/xray/目录，双击config.json文件，找到`"password": "",`，在`""`中间粘贴密钥，Ctrl+S保存。
- 使用SSH客户端软件连接你的VPS，输入`systemctl restart xray`重启Xray。