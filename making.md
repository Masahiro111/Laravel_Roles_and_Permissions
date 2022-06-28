1. Laravelのインストール

```
// インストール
laravel new project

// プロジェクトルートに移動
cd project
```

2. Laravel Breeze のインストール


```
composer require laravel/breeze

php artisan breeze:install

npm install

npm run dev

php artisan migrate
```

```
// webpack.mix.js
// webpack にバージョン情報と非通知を追加

// ...
.version()
.disableNotifications();
```

```
// Blade ファイルの 「asset」を「mix」に変更

<!-- Styles -->
<link rel="stylesheet" href="{{ mix('css/app.css') }}">

<!-- Scripts -->
<script src="{{ mix('js/app.js') }}" defer></script>
```

3. seeder ファイルの作成

```
php artisan make:seeder Admin
```

```
// database\seeders\Admin.php

<?php

namespace Database\Seeders;

use App\Models\User;
use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;

class Admin extends Seeder
{
    /**
     * Run the database seeds.
     *
     * @return void
     */
    public function run()
    {
        User::create([
            'name' => 'admin',
            'email' => 'admin@gmail.com',
            'email_verified_at' => now(),
            'password' => bcrypt('password'),
            'is_admin' => 1,
        ]);
    }
}
```

```
// database\seeders\DatabaseSeeder.php

public function run()
{
    $this->call(Admin::class);
}
```

```
php artisan db:seed
```