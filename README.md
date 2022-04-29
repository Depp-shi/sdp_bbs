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
