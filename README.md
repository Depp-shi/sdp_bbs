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
