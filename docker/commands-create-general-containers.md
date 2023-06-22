## redis container
```
sudo docker run -d --name redis -p 6379:6379 --restart unless-stopped redis
```

## mongo container
```
sudo docker run -d --name mongo -p 27017:27017 --restart unless-stopped -d mongo
```

## postgres container
```
docker run --name postgres -p 5432:5432 -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD='password' -e POSTGRES_DB=postgres -d postgres
```
