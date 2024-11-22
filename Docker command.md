To search for Docker images using the Docker CLI, you can use the docker search command. This command searches for images on Docker Hub

`docker search [OPTIONS] TERM`

`docker search nginx`

`docker search --filter=is-official=true python` #Filters for official images only

`docker pull <image-name>:tagoftheimage` #If you need to pull an image after finding it, use

`docker tag <local-image>:<local-tag> <repository>/<image-name>:<new-tag>` #Use the docker tag command to assign a new tag (name) to the image

Suppose you have a local image called my-app:latest and want to push it to your Docker Hub repository as myusername/my-app:v1.0

`docker tag my-app:latest myusername/my-app:v1.0`

`docker push <repository>/<image-name>:<tag>` #Use the docker push command to upload the image to the repository

`docker push myusername/my-app:v1.0`


To search  for images in Docker

`docker images ls -all`

`docker images ls --quite` #to only see the image ID

`docker inscept image` #To inscpect the image ID and retrieve detailed, low-level information about Docker objects such as containers, images, volumes, networks, or tasks. It outputs the information in JSON format, making it easy to parse and understand.

- Debugging: Get precise details about containers, images, or other objects.

- Troubleshooting: Identify misconfigurations or connectivity issues.

- Automation: Use JSON output in scripts for automation tasks.

Now to Build that image , and run a container using the image. We can use the follow commands - 

The docker build command is used to create a Docker image from a Dockerfile and any associated context (e.g., application files, dependencies).

How It Works:

- The Dockerfile contains instructions (e.g., FROM, COPY, RUN, CMD) that define how to build the image.
- The context includes all files and directories in the specified location, typically used for commands like COPY or ADD.
- Docker processes each instruction in the Dockerfile step-by-step, creating intermediate layers.
- The final layer is saved as a Docker image with a unique ID.

Examples : 

`docker build -t my-app:latest .`

- -t: Assigns a tag to the image (e.g., my-app:latest).
- .: Specifies the current directory as the build context.

If you to run a container using this image , you can run the following commands : 

The docker run command is used to create and start a container from a Docker image. It's the core way to execute an application within a container

How It Works:

- If the specified image isn't available locally, Docker pulls it from a registry like Docker Hub.
- Docker creates a container based on the image, allocating resources like memory, CPU, networking, and storage.
- The container executes the default command (CMD) or an overridden command provided at runtime.
- Docker tracks the container's execution state. You can start, stop, or restart it as needed.

Example : 

`docker run -d -p 8080:80 --name my-nginx nginx`

- -d: Runs the container in detached mode (background).
- -p: Maps port 8080 on the host to port 80 inside the container.
- --name: Assigns a name (my-nginx) to the container.
- nginx: The image to use.

Now to list the container that are running , we can use :

`docker ps`
will only list the container that are running. If you add `-a` after that command it wil show all the container that ran as well.
and `-q` will only show the container_ID as sometimes that's all you need.

Just like how we inscepted the image , we can do the same for the container by running the same command
`docker inscept container_name/ID`




