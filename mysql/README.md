提示：此方案适合单机简单环境启动，不适用于k8s方案

1.启动mysql容器
docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123456 --name my_mysql mysql
2. 适应远程登录配置 
docker exec -it my_mysql mysql -uroot -p123456 -e "grant all privileges on *.* to 'root'@'%';flush privileges;"
3. 验证
客户端 远程验证即可