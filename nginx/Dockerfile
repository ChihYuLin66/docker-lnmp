FROM nginx:latest


# RUN adduser --disabled-password --gecos '' nginx

# 複製配置文件
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80
EXPOSE 443

CMD ["nginx", "-g", "daemon off;"]
