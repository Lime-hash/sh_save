# 常用Linux脚本命令

#### 基本依赖

```bash
apt update -y && apt upgrade -y && apt install curl -y && apt install wget -y && apt install cron -y && apt install nano -y && apt install git -y
```

#### LXC重装系统

```bash
curl -so OsMutation.sh https://raw.githubusercontent.com/LloydAsp/OsMutation/main/OsMutation.sh && chmod u+x OsMutation.sh && ./OsMutation.sh
```

#### 科技Lion

```bash
bash <(curl -sL kejilion.sh)
```

#### Warp

```bash
wget -N https://gitlab.com/fscarmen/warp/-/raw/main/menu.sh && bash menu.sh
```

Github地址：https://gitlab.com/fscarmen/warp

#### 1panel

```bash
bash -c "$(curl -sSL https://resource.fit2cloud.com/1panel/package/v2/quick_start.sh)"
```

#### Realm中转

```bash
wget -qO- https://raw.githubusercontent.com/zywe03/realm-xwPF/main/xwPF.sh | sudo bash -s install
```

Gtihub地址：https://github.com/zywe03/realm-xwPF

#### 233boy-Singbox

```bash
bash <(wget -qO- -o- https://github.com/233boy/sing-box/raw/main/install.sh)
```

Github地址：https://github.com/233boy/sing-box

#### IP质量体检

```bash
bash <(curl -sL IP.Check.Place)
```

#### v2ray-agent

```bash
wget -P /root -N --no-check-certificate "https://raw.githubusercontent.com/mack-a/v2ray-agent/master/install.sh" && chmod 700 /root/install.sh && /root/install.sh
```

Github地址：https://github.com/mack-a/v2ray-agent

#### Docker

```bash
curl -fsSL https://get.docker.com | bash -s docker
```

#### Substore

```dockerfile
docker run -it -d \
--restart=always \
-e SUB_STORE_FRONTEND_BACKEND_PATH=/a2xmamRoZ2tzaGthZ2xkaHNna2poamdza2Q=\
-p 127.0.0.1:3001:3001 \
-v /etc/sub-store:/opt/app/data \
--name sub-store \
xream/sub-store
```
