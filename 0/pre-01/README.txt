
docker run -d --name nginx -v `pwd`/nginx.conf:/etc/nginx/nginx.conf -p 8080:80 nginx
docker run -d --name ghost --net=container:nginx --ipc=container:nginx --pid=container:nginx ghost

Nginx is now the init process of ghost container (not as good as we can)
