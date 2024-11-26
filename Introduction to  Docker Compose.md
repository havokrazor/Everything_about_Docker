Software systems out in the wild are rarely that simple. A mature software system will usually have at least a few Dockerized services, each with specific, individual configurations. 
There may be some shared third-party dependencies or some services may depend on each other, which means that they need to be initialized in a specific order. 
In a microservice architecture, there may be hundreds of services to contend with. 
The simple steps to follow for starting one or two containers become extremely tedious or even impossible for starting hundreds of containers. That's where Docker Compose comes in. 

**Docker Compose** is an independent tool that comes standard with most downloadable Docker distributions.

Using Docker Compose instead of manually configuring and initializing many individual Docker containers, developers can simplify the process down to running a **single configuration file.**
Docker Compose doesn't add any functionality to the Docker ecosystem, but it does
