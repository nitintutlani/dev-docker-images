# nitintutlani/dev-dockr-images/redis
  Use this image to run redis server. Adjusted for completely non-root access.

 ## Note:

  Exposes port 6379
  Uses USER 1001
  Data root: /data

### Pull prebuilt versions:
  docker pull nitintutlani/redis

### Running:
```
docker run -d \
-v /home/MyProjects/project-name/storage/redis:/data \
-p 6379:6379 \
-u 1000:0 \
nitintutlani/redis
```
