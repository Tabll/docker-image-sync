# Docker镜像仓库同步管理
支持同步到阿里/腾讯云的镜像仓库中


### 配置文件示例
以下的示例配置文件会：
nginx 推送到腾讯云
redis 推送到阿里云
mysql 推送到阿里云+腾讯云
```
images:
  - name: nginx
    tag: latest
    tencent: your-mirror2/nginx
  - name: redis
    tag: latest
    aliyun: your-mirror1/redis
  - name: mysql
    tag: 8.4.0
    aliyun: your-mirror1/mysql
    tencent: your-mirror2/mysql
```

>> 其中 your-mirror2/nginx 是可以自定义的镜像名称
>> tag 目前不支持自定义，tag只会保持不变

### 密钥示例
执行 Actions 前需要将密钥设置到仓库的 **Settings** -> **Secrets and variables** -> **Actions** -> **Repository secrets** 中

Repository secrets | 描述
-------- | -----
DOCKERHUB_USERNAME | `DockerHub 官方仓库` 用户名
DOCKERHUB_PASSWORD | `DockerHub 官方仓库` 密码
ALIYUN_PASSWORD | `阿里云镜像仓` 密码
ALIYUN_USERNAME | `阿里云镜像仓` 用户名
TENCENT_USERNAME | `腾讯云镜像仓` 密码
TENCENT_PASSWORD | `腾讯云镜像仓` 密码


