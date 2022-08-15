## redis container
```
sudo docker run -d --name redis -p 6379:6379 --restart unless-stopped redis
```

## mongo container
```
docker run -d --name mongo -p 27017:27017 --restart unless-stopped -d mongo
