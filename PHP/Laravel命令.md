# Laravel 11 框架知识点

## 一、路由配置



## 二、数据操作

### 2.1、迁移命令

```
// 创建迁移表
php artisan make:migration create_orders_settle_table
// 运行迁移
php artisan migrate
// 回滚最后1次迁移
php artisan migrate:rollback 
// 回滚最后5次迁移
php artisan migrate:rollback --step=5
// 回滚所有应用程序的迁移
php artisan migrate:reset
// 删除所有迁移表，再次重新运行
php artisan migrate:fresh
// 指定运行某个迁移文件
php artisan migrate --path=database/migrations/2025_06_06_161705_create_aj_repay_plan_fulls_table.php
// 指定回滚某个迁移文件
php artisan migrate:rollback --path=database/migrations/2025_06_06_161705_create_aj_repay_plan_fulls_table.php

// 重新运行某个迁移文件（先回滚再迁移）
php artisan migrate:refresh --path=database/migrations/2025_06_06_161705_create_aj_repay_plan_fulls_table.php


```

### 2.2、播种命令

```
// 生成播种机
php artisan make:seeder AdminUserSeeder
// 运行全部播种机
php artisan db:seed
//运行单个播种机
php artisan db:seed --class=AdminUsersSeeder

```

