DAY 2 Docker

Assignment 1
1. Run a docker container from "hello-world" image. 

         ```
         $ docker pull hello-world
         $ docker run e38bc07ac18e
         $ docker ps -a
         ```
         
![HELLO_WORLD](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day2-images/hello-world-container.png)

2. Pull "alpine" image from docker registry and see if image is available in your local image list.

         ```
         $ docker pull alpine
         $ docker images
         ```
         
![ALPINE_IMAGE](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day2-images/alpine-image.png)
 
3. Pull some specific version of docker "alpine" image from docker registry. 

         ```
         $ docker pull alpine:3.7
         $ docker images
         ```
         
![SPECIFIC_ALPINE](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day2-images/alpine-3.7.png)


4. Run a docker container from local image "alpine" and run an inline command "ls -l" while running container. 

         ```
         $ docker run -itd 3fd9065eaf02
         $ docker ps 
         $ docker exec -it c24e2f822382 sh -c "ls -al"
         ```
         
![ALPINE_LS-L](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day2-images/alpine-container-ls-al.png)

5. Try to take login to container created using "alpine" image.

         ``` 
         $ docker run -itd 3fd9065eaf02
         $ docker run -it 3fd9065eaf02
         ```
         
![ALPINE_LOGIN](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day2-images/container-login.png)

6. Detach yourself from the container without making it exit/container kill.

         ``` 
         $ ctrl p + ctrl q (while holding the ctrl button)
         ```

7. Check running containers and see if you can find out the stopped containers.

         ``` 
         $ docker ps -a
         ```


8. Stop running container.

         ``` 
         $ docker stop f8d83ec34c32
         ```

9. Start container that was stopped earlier.

         ```
         $ docker start f8d83ec34c32
         ```
 
10. Try to remove "alpine" image from your local system.

         ``` 
          $ docker rmi -f 3fd9065eaf02
         ```
