DAY 10 Docker

Assignment
Create a seperate docker network 'mynet' (bridge mode) and use it for below tasks.

       ```
       $ docker network create -d bridge mynet
       ```
![docker-network-ls](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day10-images/docker-network-ls.png)

Create docker image for Spring3HibernateApp

        ```
        FROM tomcat
        RUN apt-get update
        ADD Spring3HibernateApp.war /usr/local/tomcat/webapps/
        WORKDIR /usr/local/tomcat/webapps
        EXPOSE 8080
        CMD ["service tomcat start"]
        ```

![Dockerfile](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day10-images/docker-file.png)






Dockerize Spring3HibernateApp via Docker CLI
Use created image for running container 
Bind application to host machine port 80 
Persist webapps volume 
Restict memory utilization to 512M 
Container should be removed if it gets into exited state 
Run container in recently docker network 'my-net' 

                   ```
                   $ docker run -itp --rm 84:8080 -v 'source=myvol,target=/usr/local/tomcat/webapps' --memory="512m"  --network=mynet springapp
                   ```

![verify](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day10-images/phalana.png)

Dockerize Spring3HibernateApp via Docker Compose
Deploy service using created image 
Use 'my-net' network 
Bind host machine port 80 
Instead of volume mount use data volume to persist webapps directory

                   ```
                   version: '3'
services:
  springapp:
    build:
      context: /home/lovedeep/Desktop/ASSIGNMENTS/docker_prac/test
      dockerfile: Dockerfile
    networks:
      -  mynet
    ports:
      - 87:8080
    volumes:
      - myvol1:/usr/local/tomcat/webapps
volumes:
  myvol1:

networks:
  mynet:
                   ```

![docker-compose-file](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day10-images/docker-compose-file.png)
![dockercomposerun](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day10-images/docker-compose-run.png)

Dockerize Spring3HibernateApp via Docker Swarm
Setup 1 manager and 2 worker nodes 
Deploy Spring3HibernateApp stack using compose file 
Replicate service to 3 containers 
