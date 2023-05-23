# General

## Remove unused:
```bash
docker image prune
docker container prune
docker network prune
docker volume prune
# to do all
docker system prune
```

## Build image:
```bash
docker build -t $image_name:$tag .
# A little customization
docker build -t $image_name:$tag . -f $file --build-arg name=$dir_
```

## Install Docker Compose newer version:
```
sudo curl -L "https://github.com/docker/compose/releases/download/v2.18.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

## Docker login to AWS and push to AWS
```$
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin $AWS_REPO
# With particular profile
aws ecr --profile $profile_name get-login-password --region us-east-1 | docker login --username AWS --password-stdin aws_account_id.dkr.ecr.region.amazonaws.com

# push
docker push aws_account_id.dkr.ecr.region.amazonaws.com/$repo:$tag
```
