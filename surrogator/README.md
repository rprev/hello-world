## Summary

This repository contains Dockerfile and docker-compose.yml of [Surrogator](https://github.com/cweiske/surrogator).

## Usage
### Run
```
docker run -cap-add SYS_ADMIN -name some-surrogator -p 80:80 rprev/surrogator
```

### Import & Activate images
```
docker cp [path to default image] some-surrogator:/opt/surrogator/raw/default.[extension]
docker cp [path to image for user1] some-surrogator:/opt/surrogator/raw/[e-mail address of user1].[extension]
docker cp [path to image for user2] some-surrogator:/opt/surrogator/raw/[e-mail address of user2].[extension]
docker cp [path to image for user3] some-surrogator:/opt/surrogator/raw/[e-mail address of user3].[extension]
  ...
docker exec -it some-surrogator php /opt/surrogator/surrogator.php
```

## Docker Compose
```bash:docker-compose.yml
version: '2'
services:
  surrogator:
    image: rprev/surrogator
    ports:
      - "80:80"
    cap_add:
      - SYS_ADMIN
```
