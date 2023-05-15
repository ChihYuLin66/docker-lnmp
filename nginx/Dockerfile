# 基於 Nginx 官方映像檔
FROM nginx:latest

# 複製 Nginx 設定檔到容器內
COPY nginx.conf /etc/nginx/nginx.conf

# 設定工作目錄
WORKDIR /var/www/html

# 複製 Laravel 專案的 public 資料夾到容器內
# COPY public/ .

# 設定存取權限
RUN chown -R www-data:www-data /var/www/html 

# 開放 HTTP port
EXPOSE 80
EXPOSE 443

# 啟動 Nginx 伺服器
CMD ["nginx", "-g", "daemon off;"]
