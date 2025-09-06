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

