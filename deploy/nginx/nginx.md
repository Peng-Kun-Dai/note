#yum 安装nginx
```shell script
$ yum install nginx
# 启动
$ systemctl start nginx
#添加自启动
$ systemctl enable nginx
# 重启
$ nginx -s reload
```
## todo 后续配置...


统计/var/log/nginx/access.log  

统计所有接口及其访问次数  
```
    #   统计所有接口及其访问次数  
    $   awk '{print $1}' access.log |sort -n|uniq -c|sort -rn|head
        17 120.76.30.207
        17 117.29.177.106
        3 47.98.103.194
        3 167.248.133.36
        2 83.97.20.21
        2 80.82.77.232
        2 103.52.217.100
        1 95.123.41.94
        1 85.49.122.121
        1 66.240.205.34
    
    #   总访问量
    $   grep "keyword" access.log | awk "{print $NF}" | wc -l

    #   过滤某些ip之后访问量
    $   grep -vE "ip1|ip2" access.log | grep "keyword" | awk "{print $NF}" | wc -l

    #   200结果访问量
    $   grep "keyword" access.log | grep -E  "  200  " | awk "{print $NF}" | wc -l

```
