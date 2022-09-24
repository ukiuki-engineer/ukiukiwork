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

### Laravelインストール
```
[host]$ docker exec -it ukiukiwork_web bash
[web]$ composer install
```

## プロジェクト作成(メモ)
```
# Laravelインストール
[web]$ composer create-project --prefer-dist laravel/laravel ukiukiwork "8.*"
```
