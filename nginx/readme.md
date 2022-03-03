# General

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
