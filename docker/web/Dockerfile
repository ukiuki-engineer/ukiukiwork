FROM php:8.1.10-apache-bullseye

# composerのインストール
# マルチステージビルドを使用
 COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Node.jsのインストール
# マルチステージビルドを使用
# node.jsのversionに注意
COPY --from=node:14.20 /usr/local/bin /usr/local/bin
COPY --from=node:14.20 /usr/local/lib /usr/local/lib
# /optにyarn一式が入っている
COPY --from=node:14.20 /opt /opt

# RUNで指定したコマンドはイメージ作成時(=docker build時)に実行される
RUN apt-get update && \
  apt-get install -y libonig-dev libpq-dev \
  #apt-get install -y libonig-dev \
  zip git vim && \
  # PHPのExtensionをインストール
  #docker-php-ext-install pdo_mysql mysqli mbstring
  #docker-php-ext-install pdo_mysql mysqli
  docker-php-ext-install pdo_mysql mysqli pdo_pgsql

# ドキュメントルートをLaravelのpublicに変更
RUN sed -i 's!/var/www/html!/var/www/ukiukiwork/public!g' /etc/apache2/sites-available/000-default.conf

# Laravelで必要になるmodRewriteを有効化する
RUN mv /etc/apache2/mods-available/rewrite.load /etc/apache2/mods-enabled
RUN /bin/sh -c a2enmod rewrite
# CMDで指定したコマンドはコンテナ開始時(=docker start時)/作成時(=docker run時)実行される
#CMD sed -i 's!/var/www/html!/var/www/app/public!g' /etc/apache2/sites-available/000-default.conf

#EXPOSE 80


# .bashrcの設定
RUN echo "alias ls='ls -F --color=auto'" >> ~/.bashrc && \
    echo "alias ll='ls -l'" >> ~/.bashrc && \
    echo "alias la='ls -a'" >> ~/.bashrc
