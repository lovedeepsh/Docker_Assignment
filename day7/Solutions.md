DAY 7 Docker

Assignment
Install docker-compose on your machine, if not already installed. 

       ```
       $ sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
        $ sudo chmod +x /usr/local/bin/docker-compose
        $ docker-compose --version
       ```

Create a directory named wordpress on your local.

       ```
       $ mkdir wordpress
       ```
 
switch to that directory and create a file named docker-compose.yaml 

       ```
       $ cd wordpress
       $ touch docker-compose.yml
       ```

Use docker-compose version 2 to create docker-compose.yaml file. 
Create a service named "wordpress" using wordpress:latest image. 
Map port of wordpress container port 80 to host system port 8000. 
Add a parameter to restart container in case service went down. 
Within wordpress environment variable, add wordpress_db_host value along with port. 
Also add one more variable named wordpress_db_password. 
Add a volume named wordpress_data. 
*Add one more service named "db" under same docker-compose file. 
Use image named mysql with version 5.7
Use volume wordpress_data and map it to /var/lib/mysql
Enable always restart parameter.
Add environment variables named "MYSQL_ROOT_PASSWORD", "MYSQL_DATABASE", "MYSQL_USER" and "MYSQL_PASSWORD" along with corresponding values for all.
At last add a dependency of db service in wordpress service.

```
version: '3'
services:
  wordpress:
    image: wordpress:latest
    ports:
      - "8000:80"
    restart: on-failure
    environment:
      wordpress_db_host: db:3306
      wordpress_db_password: "123"
    depends_on:
      - db

  db:
    image: mysql:5.7
    volumes:
      - wordpress_data:/var/lib/mysql
    restart: on-failure
    environment:
      MYSQL_ROOT_PASSWORD: "1234"
      MYSQL_DATABASE: "lovedeep_db"
      MYSQL_USER: "lovedeep"
      MYSQL_PASSWORD: "1234"

volumes:
wordpress_data:
```

![docker-compose file](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day7-images/docker-compose-file.png)

save the file and build docker-compose.yaml and create containers for wordpress and db machine.

![docker-compose run](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day7-images/docker-run.png)

Display currently bulit containers created using docker-compose.

![display containers](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day7-images/display-containers.png)

Stop and remove your docker container using docker-compose.

![docker-compose-down](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day7-images/docker-compose-down.png)



![verification](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day7-images/verify.png)
