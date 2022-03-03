# General

## Install nginx:
```
sudo apt install nginx
```

## Create basic nginx config for gunicorn: [ref](https://www.alibabacloud.com/blog/how-to-set-up-django-with-postgres-nginx-and-gunicorn-on-ubuntu-16-04_594319)
```bash
sudo nano /etc/nginx/sites-available/gunicorn
```
inside file:
```
server {
    listen 80;
    server_name 192.168.43.192;

    location = /favicon.ico { access_log off; log_not_found off; }
    location /static/ {
        root /root/testproject;
    }

    location / {
        include proxy_params;
        proxy_pass http://unix:/root/testproject/testproject.sock;
    }
}
```
Save and close the file. Then, enable the Nginx virtual host by creating symlink:
```
sudo ln -s /etc/nginx/sites-available/gunicorn /etc/nginx/sites-enabled/
```
Next, test the Nginx for any configuration error with the following command:
```
nginx -t
```
Finally, restart Nginx by running the following command:
```
systemctl restart nginx
```

## Allow all servers:
```
server {
    listen 80;
    server_name ~^.*$;
    location / {
        include proxy_params;
        // other logic
    }
}
```


## proxy pass to localhost port
```
location / {
               proxy_set_header   X-Forwarded-For $remote_addr;
               proxy_set_header   Host $http_host;
               proxy_pass         https://localhost:3000;
       }
```
