# Nginx
# 1.Ubuntu20.04安装Nginx
## 1.1安装
```bash
# 安装
sudo apt update
sudo apt install nginx
```
## 1.2 验证
``` bash
# 验证
sudo systemctl status nginx
# active(running) 即表示服务开启
# ----------
● nginx.service - A high performance web server and a reverse proxy server
     Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
     Active: active (running) since Fri 2022-10-28 00:36:36 CST; 9h ago
       Docs: man:nginx(8)
   Main PID: 1282535 (nginx)
      Tasks: 3 (limit: 4639)
     Memory: 6.1M
     CGroup: /system.slice/nginx.service
             ├─1282535 nginx: master process /usr/sbin/nginx -g daemon on; master_process on;
             ├─1290278 nginx: worker process
             └─1290279 nginx: worker process

Oct 28 00:36:36 ls-5C1fbv23 systemd[1]: Starting A high performance web server and a reverse proxy server...
Oct 28 00:36:36 ls-5C1fbv23 systemd[1]: Started A high performance web server and a reverse proxy server.
# ---------
```
访问http:your IP, 可以见到以下页面(默认是80端口, 需要开放80端口)<br>
![nginx-1](../img/nginx-1.png)

## 1.3 配置
默认安装的情况下<br>
nginx的所有配置文件在`/etc/nginx/`
主要的配置文件是`/etc/nginx/nginx.conf`
配置`server`文件是`/etc/nginx/sites-available/default`
网页文件默认是`/var/www/html`
配置`server`, 可以有多个server
```bash
server {
	listen 80; # 监听的端口

	root /var/www/html ; # root地址
	index index.html;

	location / { # 路径
		root /var/www/country_exe/visual;
		try_files $uri $uri/ /index.html;
		location /api { 
			proxy_pass http://127.0.0.1:8901; # 设置代理
		}
	}
}
```

## 1.4 常用命令
```bash
nginx -s reload # 重新加载nginx
nginx -t # 检验配置文件语法是否正确
```