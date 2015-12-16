# nitintutlani/dev-dockr-images/nginx-php-fpm
  Use this image to serve nginx php-fpm websites. Adjusted for completely non-root usage with openshift v3 deployment details.

 ## Note:

  Exposes port 8080
  Uses USER 1001
  Project root: /home/app-root
  Nginx root: /home/app-root/public
  Mount your code to /home/app-root for faster deployment.

### Pull prebuilt versions:
  docker pull nitintutlani/nginx-php-fpm
  docker pull nitintutlani/nginx-php-fpm-dev

### Openshift s2i (source to image) scripts
  Make sure you copy openshift/.sti folder to your project root. Edit s2i scripts sensible as per your requirements.

### Running in dev mode:
```
docker run -d \
	-v /home/MyProjects/php-project:/home/app-root \
	-p 8080:8080 \
	-u 1000:0 \
	nitintutlani/nginx-php-fpm-dev \
	sh -c '${APP_ROOT}/.sti/bin/run'
```

### Running in production mode on openshift origin:
See openshift/template.md