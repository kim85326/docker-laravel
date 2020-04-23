# 練習 Docker Compose

### 測試

1. `$ docker-compose up -d`

2. 綁定 host `$ vi /etc/hosts`

   ```
   127.0.0.1 test-docker-php.com
   ```

3. 使用瀏覽器打開 `http://localhost` 會看到 Nginx 歡迎頁面，代表 Nginx 架設成功

4. 使用瀏覽器打開 `http://test-docker-php.com/hello.html` 會看到 Hello，代表 Nginx Volume 設定成功

5. 使用瀏覽器打開 `http://test-docker-php.com/info.php` 會看到 PHP 資訊頁面，代表 php-fpm 架設成功

### 使用

- 可以在 `www` 資料夾下新增 .php 檔
- 可以在 `nginx/sites` 資料夾下新增自定義的 .conf 檔
