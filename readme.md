## 環境構築
### 最初に
```
# dockerのキャッシュを消す
$ docker builer prune
```
### コンテナ起動
```
docker-compose up -d
```

### Laravelインストールと設定
```
[host]$ docker exec -it ukiukiwork_web bash
[web]$ composer install
[web]$ cp .env.example .env
[web]$ php artisan key:generate
```

## プロジェクト作成(メモ)
```
# Laravelインストール
[web]$ composer create-project --prefer-dist laravel/laravel ukiukiwork "8.*"
```
