DAY 3 Docker

Assignment 1
-------------------
## Docker Port:
1. Pull nginx image from dockerhub.

```
       $ docker pull nginx
       $ docker images
```

2. Run a container from nginx image and map container port 80 to system port 80.

``` 
        $ docker run -itdp 80:80 nginx 
```
3. Display all mapped ports on nginx image.

```
        $ docker port a6228015efe3
```

![docker](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day3-images/day3-ques3.png)

4. Run a docker container named "containexpose" from nginx image and expose port 80 of container to outer world without mapping it to any of system port.
        
        ```
        $ docker run -itd --network host --name containexpose nginx bash
        ```

## Docker Volume:
1. Create docker volume named "dbvol"
```
$ docker volume create dbvol
```
2. Run docker container from wordpress image and mount "dbvol" to /var/lib/mysql
```
$ docker pull wordpress
$ docker images
$ docker run -itd --name wordpress -v dbvol:/var/lib/mysql 06508c5f90d1 bash
```


3. Display all docker volumes.
```
$ docker volume ls
```
4. Create another docker volume named "testvol"
```
$ docker volume create testvol
```

5. Remove docker volume "testvol"
```
$ docker volume rm testvol
```

## Docker Linking:
1. Run a container in detached mode with name "db" from image "training/postgres"
```
$ docker pull training/postgres
$ docker run -itd - -name db training/postgres 
$ docker ps
```
2. Run another container in detached mode with name "web" from image "training/webapp", link container "db" with alias "mydb" to this container and finally pass an inline command "python app.py" while running container.
```
$ docker run -itd --name web --link db:mydb 6fae60ef3446 python app.py
```
3. Take a bash terminal in "web" container.
```
$ docker exec -it 42e5245d58fb bash
```

4. Test container linking by doing a ping to "mydb"
```
root@42e5245d58fb:/opt/webapp# ping mydb
```

![docker](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day3-images/ping_mydb.png)
