# Redis
### mac配置文件默认地址
```bash
/usr/local/redis-版本号/etc/redis.conf
```

### 启动redis服务
```bash
# 进入redis文件夹 (指定配置文件)
./bin/redis-server ./etc/redis.conf
```

### 设置密码
```bash
# 通过命令设置(不用重启服务)
config set requirepass 密码
# 在配置文件设置 在redis.conf文件中配置（需要重启服务）
requirepass 密码
```