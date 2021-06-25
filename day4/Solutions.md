DAY 3 Docker

Assignment 1
1. Create a file named index.js with below content. 
index.js
var os = require("os"); var hostname = os.hostname(); console.log("hello from " + hostname);

2. Create a file named Dockerfile and write code as per the steps mentioned. 
Use alpine image. 
Add Author/Maintainer name in DockerFile 
run commands -> apk update & apk add nodejs 
copy current directory to /app 
change your working directory to /app 
specify the default command to be run upon container creation as mentioned below. node index.js 

```
![Docker File](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day4-images/Docker%20file.png)
```

![DockerFile](https://github.com/lovedeepsh/Docker_Assignment/blob/master/day4/Dockerfile1)


3. Build image from Dockerfile. 

```
$ docker build -t nodejs .
```

![Docker build](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day4-images/docker%20build.png)





4. Tag image with name "hello:v0.1" 

```
$ docker image tag nodejs hello:v0.1
```

![docker images with tag](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day4-images/docker%20image.png)

![hello container](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day4-images/hello%20container.png)

Assignment 2

1. Create a DockerFile.
2. Use Ubuntu latest image.
3. Add your name as a Manintainer.
4. Update local packages using command (apt-get update).
5. Install nodejs package.
6. Install npm package.
7. Create a symlink using command (ln -s /usr/bin/nodejs /usr/bin/node).
8. Trigger a command (npm install -g http-server)
9. Add any test index.html file from local at /usr/apps/hello-docker/index.html on container.
10. change your working directory to /usr/apps/hello-docker/.
11. Run a command (http-server -s) on every container initialization.
12. Build your dockerfile and tag it with "yourname:docker-web"

![dockerfile 2](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day4-images/Dockerfile2.png)

![DockerFile](https://github.com/lovedeepsh/Docker_Assignment/blob/master/day4/Dockerfile2)


```
$ docker build -t lovedeep:docker-web .
```

![build success](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day4-images/lovedeep-docker-web.png)

![docker image 2](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day4-images/dockerimages2222.png)

13. Run a docker container from the image that you have just created and map container 8080 port to host 8080 port.(8080:8080)

```
$ docker run -itdp 80:80 82f03aa22059
```

14. Try accessing your webpage using "http://<virtualmachine_ipaddress>:8080/index.html" URL.

```
![port mapped](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day4-images/dockeroutput.png)
```

15. Delete docker container and image from local.

```
$ docker rm -f 82f03aa22059
$ docker rmi -f 82f03aa22059
```
