## build by bin

```
# 构建镜像
# 在 etcd-docker 目录执行构建命令：
# 构建镜像，标签为 bitnami/etcd:3.5.10（与官方命名一致）
docker build -t bitnami/etcd:3.5.10 .


# 若下载二进制包超时，可手动下载后构建：
# 1. 手动下载包：wget https://github.com/etcd-io/etcd/releases/download/v3.5.10/etcd-v3.5.10-linux-amd64.tar.gz
# 2. 修改 Dockerfile：将 curl 下载行替换为 COPY 本地包
# COPY etcd-v3.5.10-linux-amd64.tar.gz /tmp/
# RUN tar -xz --st		rip-components=1 -C /usr/local/bin/ -f /tmp/etcd-v3.5.10-linux-amd64.tar.gz etcd-v3.5.10-linux-amd64/etcd etcd-v3.5.10-linux-amd64/etcdctl etcd-v3.5.10-linux-amd64/etcdutl


# 验证镜像
# 查看镜像是否构建成功
docker images | grep bitnami/etcd

# 启动容器测试
docker run --rm bitnami/etcd:3.5.10 etcd --version
# 输出如下即成功：
# etcd Version: 3.5.10
# Git SHA: 000000000
# Go Version: go1.19.10
# OS/Arch: linux/amd64
```