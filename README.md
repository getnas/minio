# minio docker image for arm32v6 architecture

本镜像基于 [minio](https://github.com/minio/minio) 官方 `Dockerfile` 修改而来，构建适用用于树莓派 3B 的 Docker 镜像。

## 快速使用

```shell
sudo docker run --name minio -d \
    -p 9000:9000 \
    -v /mnt/data:/data \
    -v /mnt/config:/root/.minio \
    getnas/minio:arm32v6 server /data
```

`/mnt/data` 为本地映射到容器的数据存储目录，`/mnt/config` 为本地映射到容器的 minio 配置文件目录，容器运行后，可以在该目录中的 `config.json` 文件中找到程序初始生成的 `Access Key` 和 `Secret Key`。

> 注意：访问 minio 服务器需要通过 `Access Key` 和 `Secret Key` 验证身份。

## 浏览器访问

浏览器输入 `host-ip:9000` 即使用主机 IP 地址或域名的 6000 号端口通过浏览器访问 minio 服务。

更多详细用法请参考 `minio` 官方手册。