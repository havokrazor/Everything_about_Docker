### You might run into this trouble more often when some of your container is running really slow , there's multiple advanced commands you can run to resolve this issue. But we will look at few of these commands here ###

First let's create a sample container to test all of these container 

`docker run --name=alpine --entrypoint=sleep -d alpine infinity` 

The container starts in the background, runs the sleep infinity command (keeping the container running indefinitely), and is named alpine.

`Docker stats containername` can give you a snapshot of the container's performance as it is running.

`Docker top containername` shows whats running inside the container without having to exec into it

`Docker inspect containername` this can show you advanced information about container that's running in a JSON format


