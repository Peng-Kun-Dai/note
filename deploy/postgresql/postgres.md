#postgres 首次安装使用
[postgres官网](https://www.postgresql.org/download)
```shell script
# 
$ 
# 查看系统版本
$ cat /proc/version
# 在官网根据系统生成自己的安装脚本
# 以下是我的安装脚本
dnf install -y https://download.postgresql.org/pub/repos/yum/reporpms/EL-8-x86_64/pgdg-redhat-repo-latest.noarch.rpm
dnf -qy module disable postgresql
dnf install -y postgresql12-server
/usr/pgsql-12/bin/postgresql-12-setup initdb
systemctl enable postgresql-12
systemctl start postgresql-12

# 执行上述代码，完成安装

# 修改配置，支持远程访问
# 目录：/var/lib/pgsql/12/data 下pg_hba.conf和postgresql.conf

# 初次使用 ...
#常用命令
\h:                 //查看SQL命令的解释 比如\h select
\?:                 //查看psql命令列表
\l:                 //列出所有数据库
\c [database_name]: //连接其他数据库
\d:                 //列出当前数据库的所有表格
\d [table_name]:    //列出某一张表格的结构
\du:                //列出所有用户
\e:                 //打开文本编辑器
\conninfo:          //列出当前数据库和连接的信息


#切换系统postgres用户
sudo su - postgres

#数据导出
pg_dump -h localhost -U postgres(用户名) 数据库名(缺省时同用户名)   >/data/dum.sql
pg_dump  数据库名  >/data/dum.sql

#数据导入
CREATE USER dbuser WITH PASSWORD 'password';
CREATE DATABASE exampledb OWNER dbuser;
GRANT ALL PRIVILEGES ON DATABASE exampledb to dbuser;
\q
psql exampledb < exampledb.sql



```