DAY 2 Docker

Assignment 2
1. Again pull "alpine" image from docker registry.

        ```
        $ docker pull alpine:3.7
        ```

2. Take interactive login to bash while running docker container from "alpine" image.

        ```
        $ docker run -it 3fd9065eaf02
        ```

3. Run command inside container: echo "hello world" > hello.txt ls

        ```
        $ docker pull alpine:3.7
        $ docker run -itd 3fd9065eaf02
        $ docker run -it 3fd9065eaf02
        /# echo “hello world” > hello.txt
        /# ls
        ```
![COMMAND](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day2-images/ass2-q3.png)
![COMMAND2](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day2-images/assignmentB-ques3.png)
 
4. Take exit from same container without killing the container.
        
        ```
        $ ctrl p+q 
        ```

5. Run another container using below command and check if you can find hello.txt within this container. You should find container isolations from step 3-5. docker container run alpine ls
Yes, I found nothing inside the newly created container.

![CHECKING](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day2-images/assignentB-ques5.png)

 
6. Stop a container using Container ID. 
        
         ```
         $ docker stop b1d53d469d7b
         ```


7. Start same container using ID and exec a command "echo 'hello world!'" in docker container without instantiating a new container. 
         
         ```
         $ docker start b1d53d469d7b
         $ docker exec -it b1d53d469d7b ash
         /# ls
         /# echo ‘hello world!’
         ```
         
![START](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day2-images/assignmentB-ques7.png)

8. Inspect already downloaded "alpine" docker image using docker inspect command.
         
         ```
         $ docker image inspect alpine
         ```
 
9. Tag your local "alpine" image with name "myimage" along with version 1.0
         
         ```
         $ docker images
         $ docker image tag 3fd9065eaf02 myimage:v1.0 
         ```
         
![TAG](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day2-images/assignmentB-ques9.png)

