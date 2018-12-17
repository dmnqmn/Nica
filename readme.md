Sever线下环境快速搭建

（建议直接联系qumeina 要一下搭建环境的配置conf）

1. git clone 代码库
2. 到项目目录下，执行 docker run --rm -v $(pwd):/app composer install
3. sudo chown -R $USER 项目laravel-app
4. docker-compose.yml Dockerfile 放在项目目录
5. ln -s .env.example .env
6. 把 .env 的数据库内容改一下 
7. 项目目录下增加 php/local.ini mysql/my.cnf nginx/conf.d/app.conf
8. 到项目目录下，执行 docker-compose up -d
9. docker ps 看一下都跑起来没有
10. .env 的 DB_HOST 值 改成 db
11. docker-compose exec app php artisan key:generate
12. docker-compose exec app php artisan config:cache
13. docker-compose exec app php artisan migrate
14. 进入mysql:  docker-compose exec db mysql -uroot -plaravel

