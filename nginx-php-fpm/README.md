# nitintutlani/dev-dockr-images/nginx-php-fpm
  Use this image to serve nginx php-fpm websites. Adjusted for completely non-root usage.

 ## Note:

  Exposes port 8080
  Uses USER 1001
  Project root: /home/app-root
  Nginx root: /home/app-root/public
  Mount your code to /home/app-root for faster deployment.
