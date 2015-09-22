# nitintutlani/dev-dockr-images/nginx-php-fpm
  Use this image to serve nginx php-fpm websites. Adjusted for completely non-root access.

 ## Note:

  Exposes port 8080
  Uses USER 1001
  Project root: /home/app-root
  Nginx root: /home/app-root/public
  Allows running `npm install -g *` without sudo. Saves NPM cache to /var/app-root/.npm/cache and global deps to /var/app-root/.npm/global
  Mount persistent volume to /var/app-root for faster deployment.

Alternate, use wth openshift s2i builder:
  Preserve artifacts under /var/app-root/.npm
