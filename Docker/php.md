## 1、Dockerfile

```
FROM php:8.3.21-fpm-alpine3.20

# 1. 使用国内镜像源
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories

# 2. 安装系统依赖
RUN apk update && apk add --no-cache \
    # 运行时依赖
    libzip \
    libpng \
    libjpeg-turbo \
    freetype \
    openssl \
    postgresql-libs \
    unzip \
    git \
    # 构建依赖
    libzip-dev \
    libpng-dev \
    libjpeg-turbo-dev \
    freetype-dev \
    openssl-dev \
    postgresql-dev


# 4. 安装PHP扩展
RUN docker-php-ext-configure gd --with-freetype --with-jpeg && \
    docker-php-ext-install -j$(nproc) \
    pdo_mysql \
    pdo_pgsql \
    zip \
    bcmath \
    opcache


WORKDIR /var/www
COPY . .
```

**备注：**注意使用本地镜像（ php:8.3.21-fpm-alpine3.20 ）和联网镜像 （ php8.3.21-fpm-alpine3.20 ）

## 2、Docker-compoer

```
version: '3.8'

services:
  php:
    image: raycake-php83-fpm:latest
    container_name: raycake-php
    restart: unless-stopped
    working_dir: /var/www
    volumes:
      - ./:/var/www
    ports:
      - "8080:8080"
      - "9051:9051"
```

3、Docker-run

```
docker build --pull=false -t my-app .

```

