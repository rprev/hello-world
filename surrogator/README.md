## Summary

This repository contains Dockerfile of [Surrogator](https://github.com/cweiske/surrogator).

## Usage
### Run
```
docker run -cap-add SYS_ADMIN -name some-surrogator -p 80:80 rprev/surrogator
```

### Import & Activate images
```
docker cp [path of your image] some-surrogator:/opt/surrogator/raw/default.[extension]
docker cp [path of your image] some-surrogator:/opt/surrogator/raw/[mail address 1].[extension]
docker cp [path of your image] some-surrogator:/opt/surrogator/raw/[mail address 2].[extension]
docker cp [path of your image] some-surrogator:/opt/surrogator/raw/[mail address 3].[extension]
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
