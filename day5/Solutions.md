DAY 4 Docker

Assignment
Signup on dockerhub. 

![Dockerhub login](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day5-images/myrepo.png)

Login on dockerhub and create a repository by providing repo name "mytestrepo" and a little description about the same.

![mytestrepo](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day5-images/test-repo.png)
 
Search for "centos" image on docker using commandline.

        ```
        $ sudo docker search centos
        ```
 
![docker search](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day5-images/docker%20search.png)

Limit out search result to 10 entries only. 

        ```
         $ sudo docker search centos --limit 10
        ```

![docker search limit](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day5-images/limit_10.png)

Apply a filter on search result to show entries for images having 3 stars. 

        ```
         
        ```

![docker filter]()

Format the search result to get output containing only name,description and is_official values. 

        ```
        $ sudo docker search --format "{{.Name}}:{{.Description}}:{{.IsOfficial}}" centos
        ```

![docker format](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day5-images/docker-search-format.png)

Pull an image named "centos" from dockerhub. 

        ```
        $ sudo docker pull centos
        ```
       
![docker pull](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day5-images/docker-pull.png)

Tag "centos" image with name "mycentos" in your repository with version 1.1 

        ```
        $ sudo docker image tag centos lovedeep/mycentos:v1.1
        ```

![docker tag](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day5-images/docker-tag.png)

Push that image to your repo "mytestrepo" on your dockerhub. 

        ```
        $ sudo docker push lovedeep/mycentos:v1.1
        ```

![docker login](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day5-images/docker-login.png)

![docker push](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day5-images/docker-push.png)

Do commandline logout on dockerhub. 

        ```
        $ sudo docker logout
        ```

![docker logout](https://github.com/lovedeepsh/Docker_Assignment/blob/master/Docker-day5-images/docker-logout.png)
