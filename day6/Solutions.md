DAY 6 Docker

Assignment
Install docker-compose on your machine, if not already installed.

        ```
        $ sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
        $ sudo chmod +x /usr/local/bin/docker-compose
        ```

Check docker-compose version.

        ```
        $ docker-compose --version
        ```
![docker version](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day6-images/Docker-version.png)

Create a directory named nginx in your root.

Switch to that directory and create a file named docker-compose.yaml

        ```
        $ mkdir nginx
        ```
![nginx created](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day6-images/nginxcreated.png)


Use docker-compose version 2 to create docker-compose.yaml file.

Create a service named "databases".

Use image named "mysql"

Map container 3306 port to host machine 3306 port.

Add environment variables named "MYSQL_ROOT_PASSWORD", "MYSQL_DATABASE", 

"MYSQL_USER" and "MYSQL_PASSWORD" along with corresponding values for all.

Add another service named "web"

Use image "nginx"


       ```
       version: '2'
       services:
         databases:
         image: "mysql"
         ports:
            - "3306:3306"
         environment:
            - MYSQL_ROOT_PASSWORD=123
            - MYSQL_DATABASE=lovedeep_sharma
            - MYSQL_USER=root
            - MYSQL_PASSWORD=123

        web:
        image: nginx
        ports:
            - "80:80"
        depends_on:
            - databases

    ...
       ```

![docker-compose-file](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day6-images/docker-compose-file.png)

Save docker-compose.yaml file and do docker-compose up.

![docker-compose-up](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day6-images/Docker-compose-up.png)

Verify nginx service is up and is accessible on machine.

![nginx-verification](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day6-images/nginx.png)

Stop and remove your docker container using docker-compose.

        ```
         $ docker-compose down
        ```

![docker-compose-down](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day6-images/docker-compose-down.png)
