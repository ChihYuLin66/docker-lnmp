FROM nginx:latest

# 複製配置文件
COPY nginx.conf /etc/nginx/nginx.conf

# 設置網站文件目錄
# WORKDIR /var/www/html

# 將本地網站文件複製到容器中
# COPY ./html/ .

CMD ["nginx", "-g", "daemon off;"]


EXPOSE 80
EXPOSE 443
