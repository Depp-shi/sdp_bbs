ssh-keygen -C '邮箱' -t rsa
mkdir resources/views/layouts  
touch resources/views/layouts/app.blade.php  
touch resources/views/layouts/_header.blade.php  
touch resources/views/layouts/_footer.blade.php  
mkdir resources/views/shared  
touch resources/views/shared/_messages.blade.php  
mkdir resources/views/pages  
touch resources/views/pages/root.blade.php  
php artisan make:controller PagesController  
composer require laravel/ui:3.4.5 --dev  
php artisan ui bootstrap  
npm config set registry=https://registry.npm.taobao.org  
yarn config set registry https://registry.npm.taobao.org  
SASS_BINARY_SITE=http://npm.taobao.org/mirrors/node-sass yarn  
yarn add resolve-url-loader@^5.0.0 --dev  
npm run watch-poll  
yarn add @fortawesome/fontawesome-free
composer require "overtrue/laravel-lang:~6.0"  
composer require "mews/captcha:~3.0"  
php artisan vendor:publish --provider='Mews\Captcha\CaptchaServiceProvider'  
##缺少gd库时  
apk add libpng-dev libwebp-dev libjpeg-turbo-dev freetype-dev  
php7.4后有变化  
docker-php-ext-configure gd --with-webp=/usr/include/webp --with-jpeg=/usr/include --with-freetype=/usr/include/freetype2/  
docker-php-ext-install gd  

git checkout app/Http/Controllers/PagesController.php

php artisan make:middleware EnsureEmailIsVerified


mkdir -p /usr/share/zoneinfo/Asia
docker cp /usr/share/zoneinfo/Asia/Shanghai local-php-fpm:/usr/share/zoneinfo/Asia/Shanghai
ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime


php artisan make:controller UsersController  


mkdir resources/views/users  
touch resources/views/users/show.blade.php  
touch resources/views/users/edit.blade.php  

php artisan make:migration add_avatar_and_introduction_to_users_table --table=users  

php artisan make:request UserRequest


composer require "intervention/image:^2.7"  
php artisan vendor:publish --provider="Intervention\Image\ImageServiceProviderLaravelRecent"  
php artisan make:policy UserPolicy  


php artisan make:model Category -m  

php artisan make:migration seed_categories_data  


composer require "summerblue/generator:9.*" --dev  


git checkout .  
git clean -f -d  


php artisan make:scaffold Topic --schema="title:string:index,body:text,user_id:bigInteger:unsigned:index,category_id:integer:unsigned:index,reply_count:integer:unsigned:default(0),view_count:integer:unsigned:default(0),last_reply_user_id:integer:unsigned:default(0),order:integer:unsigned:default(0),excerpt:text:nullable,slug:string:nullable"  

touch resources/views/topics/_topic_list.blade.php  
touch resources/views/topics/_sidebar.blade.php  

composer require "barryvdh/laravel-debugbar:~3.6" --dev  

php artisan vendor:publish --provider="Barryvdh\Debugbar\ServiceProvider"  


composer require "summerblue/laravel-active:9.*"  


touch resources/views/users/_topics.blade.php  

mkdir -p resources/editor/css  
mkdir -p resources/editor/js  

touch public/uploads/images/topics/.gitignore  
touch resources/sass/_topic_body.scss


fetch("http://www.sdpbbs.local/topics", {"headers":{"content-type":"application/x-www-form-urlencoded","upgrade-insecure-requests":"1"},"body":"_token=y6Aam91YhaqDJehQAQfzQUyophK52Rx7iIglv49F&title=dangerous%20content+&category_id=2&body=%3Cscript%3Ealert%28%27%E5%AD%98%E5%9C%A8%20XSS%20%E5%AE%89%E5%85%A8%E5%A8%81%E8%83%81%EF%BC%81%27%29%3C%2Fscript%3E","method":"POST","mode":"cors"});


composer require "mews/purifier:~3.3"   
php artisan vendor:publish --provider="Mews\Purifier\PurifierServiceProvider"  

composer require "overtrue/pinyin:~4.0"  
composer require "predis/predis:~1.1"  
php artisan make:job TranslateSlug  

php artisan queue:listen
composer require "laravel/horizon:~5.9"  
php artisan vendor:publish --provider="Laravel\Horizon\HorizonServiceProvider"  
php artisan horizon  
http://www.sdpbbs.local/horizon  
php artisan make:scaffold Reply --schema="topic_id:integer:unsigned:default(0):index,user_id:bigInteger:unsigned:default(0):index,content:text"  
touch resources/views/topics/_reply_box.blade.php  
php artisan notifications:table  
php artisan make:migration add_notification_count_to_users_table --table=users  

php artisan make:notification TopicReplied  
Route::resource('notifications', 'NotificationsController', ['only' => ['index']]);  
php artisan make:controller NotificationsController  
mkdir resources/views/notifications  
touch resources/views/notifications/index.blade.php  
mkdir resources/views/notifications/types  
touch resources/views/notifications/types/_topic_replied.blade.php  


composer require "spatie/laravel-permission:~5.5"  

php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider" --tag="migrations"  
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider" --tag="config"  


composer require "viacreative/sudo-su:~1.1"  
php artisan vendor:publish --provider="VIACreative\SudoSu\ServiceProvider"  

composer require "summerblue/administrator:9.*"  
php artisan vendor:publish --provider="Frozennode\Administrator\AdministratorServiceProvider"  

mkdir -p config/administrator/settings  
touch config/administrator/settings/.gitkeep  
touch config/administrator/users.php  
touch config/administrator/roles.php  
touch config/administrator/permissions.php  


git add -A  
git commit -m "管理员可以管理权限和角色"  

touch config/administrator/categories.php  

touch config/administrator/topics.php  
touch config/administrator/replies.php
touch config/administrator/settings/site.php  
touch resources/views/pages/permission_denied.blade.php  
