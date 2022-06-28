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