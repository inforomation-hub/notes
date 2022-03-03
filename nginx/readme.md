# General

## Create basic nginx config for gunicorn
```bash
nano /etc/nginx/sites-available/gunicorn
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
ln -s /etc/nginx/sites-available/gunicorn /etc/nginx/sites-enabled/
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
