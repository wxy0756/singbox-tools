# socks5 安装脚本
## 1、 socks5 安装以及卸载
 1.1、安装（可覆盖安装，端口号不指定则会随机端口，用户名和密码不指定也会随机生成）：
 ```bash
 PORT=端口号 USERNAME=用户名 PASSWORD=密码 bash <(curl -Ls https://raw.githubusercontent.com/jyucoeng/singbox-tools/refs/heads/main/socks5.sh)
```

1.2、socks5 卸载：
 ```bash
bash <(curl -Ls https://raw.githubusercontent.com/jyucoeng/singbox-tools/refs/heads/main/socks5.sh) uninstall
 ```

1.3、socks5 节点查看：
 ```bash
bash <(curl -Ls https://raw.githubusercontent.com/jyucoeng/singbox-tools/refs/heads/main/socks5.sh) node
 ```

