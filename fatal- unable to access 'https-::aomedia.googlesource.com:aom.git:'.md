## fatal: unable to access 'https://aomedia.googlesource.com/aom.git/': Failed to connect to aomedia.googlesource.com port 443: Operation timed out

## 系统环境:Macos 10.11.6
## 安装ffmpeg依赖时出错，系统已经全局代理

### 猜想：被墙了
### 猜想：google能上，但是git clone的时候出错，原因未知
### 原因未知

查看本地代理的转发端口

执行git config --global http.proxy http://127.0.0.1:你的代理端口

done

