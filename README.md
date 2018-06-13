# docker-Brat

A docker project to download, unpack and run the Brat web application. 

Brat - Brat Rapid Annotation Tool is an online environment for collaborative text annotation. This docker project is implemented to dockerize the application and run using docker on any server or laptop.

#### Installation Requirements:
	
- [Docker](https://docs.docker.com/install/) installed on the system 
- Operating systems: Linux, MacOS or Windows
- System requirements: minimum 8GB of memory

Brat login requires username, password and admin email to be mentioned by the user. These arguements are specified in the dockerfile. User is required to provide the values while builing the dockerfile.

To build the dockerfile: 

	$ docker build --build-arg username=<Username> --build-arg password=<Password> --build-arg admin_email=<email ID> -t brat .

> `<Username>`, `<Password>` and `<email ID>` are login credentials to be provided by the user

To run the built image: 

	$ docker run --name brat_instance -p 80:80 -d brat

To open the application:

Open the browser and enter the address : http://localhost/brat-v1.3_Crunchy_Frog/

To stop all running containers: 
```
docker stop $(docker ps -aq)
```

To remove and refresh the installation: 
```
docker rm $(docker ps -aq)
```

To remove the running brat container:
```
docker stop brat_instance

docker rm brat_instance
```

To remove the brat image:
```
docker rmi [-f] brat
```