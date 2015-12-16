# nitintutlani/dev-docker-images/alpine-node
  Use this image to serve node projects. Adjusted for completely non-root usage with openshift v3 deployment details.

 ## Note:

  Exposes port 3000
  Uses USER 1001
  Project root: /home/app-root
  Mount your code to /home/app-root for faster deployment.

1. Pull nitintutlani/alpine-node image
	`docker pull nitintutlani/alpine-node`
2. Run/create nodejs container
```
	docker run -d \
	-v /home/your-project-folder:/home/app-root \
	-p 3000:3000 \
	-u 1000:0 \
	--name my-app-dev \
	nitintutlani/alpine-node \
	gulp start
```
To start app container at a later time, `docker start my-app-dev`.
PS: Replace `gulp start` with any suitable start command. I use `gulp start` task to start a `nodemon` based server script.
```
gulp.task('start', function () {
  nodemon({
    script: 'server/server.js'
  , ext: 'js'
  , env: { 'NODE_ENV': 'development' }
  });
});
```

For production depo\loyment in openshift we need to use: `sh -c '${APP_ROOT}/.sti/bin/run'` as run script.
	docker run -d \
	-v /home/your-project-folder:/home/app-root \
	-p 3000:3000 \
	-e NODE_ENV=production \
	-u 1000:0 \
	--name my-app \
	nitintutlani/alpine-node \
	sh -c '${APP_ROOT}/.sti/bin/run'

3. First time only:
	`docker exec -it my-app sh -c '${APP_ROOT}/.sti/bin/assemble'`
Using above we can easily perform other tasks:
	`docker exec -it localityshopApi gulp test`
