#Docker Configuration for laravel app 

- clone this repo
- docker-compose up -d
- docker-compose exec app bash // now you are inside your server dir 
# configure db
-       cp .env.example .env
-       docker-compose exec app php artisan key:generate
-       docker-compose exec app php artisan config:cache
-       docker-compose exec db bash
  ##### run this sql cmd 
  -     mysql -u root -p // password = your_mysql_root_password
  -     GRANT ALL ON laravel.* TO 'laraveluser'@'%' IDENTIFIED BY 'your_laravel_db_password';
  -     FLUSH PRIVILEGES;
  -     exit; 
  -     exit;
  
  ## note :
  remember if you change any thing in db name or password exec this cmd
   
   ``docker-compose exec app php artisan config:cache``
  -     docker-compose exec app php artisan migrate
  
  #Now you are ready to go
   
  ``localhsot\register``