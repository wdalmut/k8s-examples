docker run -d --name pause -p 8080:80 --ipc=shareable gcr.io/google_containers/pause-amd64:3.0

cat <<EOF >> nginx.conf
error_log stderr;
events { worker_connections  1024; }
http {
    access_log /dev/stdout combined;
    server {
        listen 80 default_server;
        server_name example.com www.example.com;
        location / {
            proxy_pass http://127.0.0.1:2368;
        }
    }
}
EOF
docker run -d --name nginx -v `pwd`/nginx.conf:/etc/nginx/nginx.conf --net=container:pause --ipc=container:pause --pid=container:pause nginx

docker run -d --name ghost --net=container:pause --ipc=container:pause --pid=container:pause ghost
