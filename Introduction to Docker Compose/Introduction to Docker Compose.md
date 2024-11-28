Software systems out in the wild are rarely that simple. A mature software system will usually have at least a few Dockerized services, each with specific, individual configurations. 
There may be some shared third-party dependencies or some services may depend on each other, which means that they need to be initialized in a specific order. 
In a microservice architecture, there may be hundreds of services to contend with. 
The simple steps to follow for starting one or two containers become extremely tedious or even impossible for starting hundreds of containers. That's where Docker Compose comes in. 

**Docker Compose** is an independent tool that comes standard with most downloadable Docker distributions.

Using Docker Compose instead of manually configuring and initializing many individual Docker containers, developers can simplify the process down to running a **single configuration file.**

Understanding configuration as code is core to understanding Docker Compose. Configuration means all of the settings that allow the system to run, such as where persistent data lives, how to access and send messages to other internal and external services, and what environment-specific values to use.

Docker Compose is a declarative tools (just like terraform) which allow you to specify the desired end result and will execute any steps to reach that result automatically. 

Docker compose is ...

| Designed for     | Not Designed for |
|----------|-----|
| Local Devlopment    | Distributed system  |
| Staging server      | Not used to run container across multiple hosts  |
| Continuous integration/testing environment  | Complex production environment  |

Every Docker Compose configuration must be in a ##YAML## file format and be saved under the file name, `docker-compose.yaml`.

Wrintg a Docker compose configuration : A Docker compose file will normally consist of 

- Version

   Typically the first line will specify which version of Docker Compose is being used.

- Services

   Services is used to specify all of the containers the application needs to run. Keys to define within a service:
   - image: Specifies the Docker image to use (e.g., nginx, postgres).
   - build: Specifies the Dockerfile and context to build the image.
   - ports: Maps host ports to container ports (e.g., 8080:80).
   - volumes: Defines volumes or bind mounts.
   - depends_on: Specifies service dependencies.
   - environment: Sets environment variables.

These are the most commonly used Docker Compose commmands , 

|Command |	Description |
|--------|--------------|
|docker-compose up |	Start all services. |
|docker-compose down |	Stop and remove all services and resources. |
|docker-compose ps |	List running services. |
|docker-compose logs |	View logs of services. |
|docker-compose exec |	Execute a command in a running service. |
|docker-compose build |	Build or rebuild service images. |
|docker-compose start |	Start stopped containers. |
|docker-compose stop |	Stop running containers. |
|docker-compose restart |	Restart containers. |
|docker-compose pull |	Pull the latest images. |
|docker-compose rm |	Remove stopped containers. |
|docker-compose config |	Validate and display the Compose file. |
|docker-compose scale |	Scale services to multiple instances. |
|docker-compose run |	Run a command or one-off container. |
|docker-compose version |	Display Docker Compose version information. |
