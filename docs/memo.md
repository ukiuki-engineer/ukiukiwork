- Laravelプロジェクトの作成
```
composer create-project laravel/laravel=6.18.* プロジェクト名
```

- サーバ起動
```
php artisan serve --host 0.0.0.0
```

- vueのインストール
```
npm install -D vue
npm install -D vue-template-compiler
```

- vueを使う
  - vueコンポーネントを作る
  - resources/js/app.jsの編集

- artisanコマンドの一覧表示
```
php artisan list
```

- db接続テスト
```
php artisan tinker
DB::connection()->getConfig();
DB::connection()->getPdo();
```

- migrationファイル作成
```
php artisan make:migration filename
```
- Model作成
```
php artisan make:model Eloquents/<modelname>
```

- nuxtプロジェクトの作成
```
$ yarn create nuxt-app client/
? Project name: ukiukiwork
? Programming language: JavaScript
? Package manager: Yarn
? UI framework: Vuetify.js
? Nuxt.js modules: (Press <space> to select, <a> to toggle all, <i> to invert selection)
? Linting tools: (Press <space> to select, <a> to toggle all, <i> to invert selection)
? Testing framework: None
? Rendering mode: Single Page App
? Deployment target: Server (Node.js hosting)
? Development tools: (Press <space> to select, <a> to toggle all, <i> to invert selection)
? What is your GitHub username? 
? Version control system: Git
```
