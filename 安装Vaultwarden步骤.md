**建议使用Typora打开**



**VPS配置要求：**

​	CPU：**1核**

​	内存：**512MB及以上**

​	硬盘：**5G及以上的存储空间**



#### **1.准备工作 (使用root用户)**

（需安装CloudFlare Tunnel、Docker-compose）

```bash
apt update -y
```

```bash
apt upgrade -y
```

```bash
apt install docker.io docker-compose -y
```

#### 2.创建 Docker Compose 配置

新建目录并创建配置文件：

```bash
mkdir vaultwarden && cd vaultwarden
```

```bash
nano docker-compose.yml
```

docker-compose.yml 配置如下：

```yaml
version: '3'
services:
  vaultwarden:
    image: vaultwarden/server:latest
    container_name: vaultwarden
    restart: always
    ports:
      - "127.0.0.1:8000:80"  # 仅本地访问（通过Cloudflare Tunnels 映射）
    volumes:
      - ./data:/data          # 持久化存储数据
      - /etc/localtime:/etc/localtime:ro  # 挂载主机时间
    environment:
      DOMAIN: "https://your-domain.com"  # 替换为你的子域名（通过Cloudflare Tunnels 映射的域名）
      SIGNUPS_ALLOWED: "true"          # 公开注册（先可以开启到后面可以关掉）
      ADMIN_TOKEN: "your-strong-token"   # 管理后台密码（必填）
      TZ: "Asia/Shanghai"  # 添加时区设置
```

ADMIN_TOKEN如果没有设置，可以生成一个强密码：

```bash
openssl rand -base64 32
```

#### 3.拉取镜像并启动Vaultwarden

```bash
docker-compose up -d
```

#### 4.通过Cloudflare Tunnels 映射

**在Cloudflare里找到Zero Trust**

**点击 网络 -> Tunnels**

**创建隧道**

**类型选HTTP，URL填localhost:端口，再在Linux系统里安装Cloudflared即可**

#### 4.注册Vaultwarden账号并关闭注册

**请先注册账号再进行以下操作！！！**

**关闭注册（最大化保护网站及数据）**

```bash
# 进入 vaultwarden 目录
cd vaultwarden

# 修改 docker-compose.yml
nano docker-compose.yml

# 关闭注册（改为 false）
SIGNUPS_ALLOWED: "false"

# 重启服务
docker-compose down
docker-compose up -d
```

**访问你的域名即可使用**

#### 5.Nano编辑器常用快捷键

|  快捷键  |                    描述                    |
| :------: | :----------------------------------------: |
| Ctrl + X | 退出编辑器（如果有未保存修改则会提示保存） |
| Ctrl + O | 保存文件（如果是新文件，会提示输入文件名） |

