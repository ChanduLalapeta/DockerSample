# DockerSample

This repo demos a sample docker image building and running as container for a .net core application.
To build a docker image and container, docker needs to be installed on your local machine(I installed windows version).

Below are the steps to successfully build this project,

1. Install Docker on your local machine.
2. Install dotnet core to build this project on your locl machine.
3. Clone the repository to local machine.
4. Navigate to App folder in command prompt and run command 'dotnet run' to build and run the project.  
5. Cntl + C to stop the program running.
6. 'dotnet publish -c Release' , run this command to publish the artifacts to release folder.
7. Run 'docker images' command to list the images available in your local docker repository.
8. Run 'docker build -t counter-image -f Dockerfile .' , command to build an image with tag 'counter-image' using the dockerfile 'Dockerfile' available in the current directory '.'.
9. Now run the command 'docker images' and you should see a new docker image as 'counter-image' now.
10. Run 'docker ps -a' command to list all the container and its statuses in your local docker.
11. Create a container using command 'docker create --name core-counter counter-image' where 'core-counter' is the container name using 'counter-image' image.
12. Now run the command 'docker ps -a' again to list the containers and you should see a new container 'core-counter' you created.
13. Run command 'docker start core-counter' to start the container.
14. Run 'docker attach core-counter' to connect to container and see the work of the container, as this is a console application you should see the counter increments.You can use cntl+C to return to command prompt.
15. Run 'docker stop core-counter' to stop the container.
16. Run 'docker rm core-counter' to remove the container from machine and by running 'docker ps -a', you don't see the container in the list.
17. Instead of creating the container, you can directly run the image by running 'docker run counter-image 3', as we passed 3 as parameter we expect 3 counters.Here the docker gives a default names to container.
18. To remove the 'counter-image' image run the command 'docker rmi counter-image:latest', make sure this image is not referenced any containers. In that case you need to delete the container first by running 'docker rm 'containername''




 

