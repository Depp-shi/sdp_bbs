mkdir resources/views/layouts  
touch resources/views/layouts/app.blade.php  
touch resources/views/layouts/_header.blade.php  
touch resources/views/layouts/_footer.blade.php  
mkdir resources/views/shared  
touch resources/views/layouts/_messages.blade.php
mkdir resources/views/pages
touch resources/views/pages/root.blade.php
php artisan make:controller PagesController
