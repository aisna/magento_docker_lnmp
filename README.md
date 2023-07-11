docker-compose up -d #后台启用容器
docker-compose down #关闭窗口
docker exec -it sin-php /bin/bash #进入php容器
如composer install 报版本过高，进入容器执行 composer self-update --1，回滚到1版本，再执行composer install 就可以安装magento

<目录建议>
代码目录：/data/web
容器目录：/data/docker
