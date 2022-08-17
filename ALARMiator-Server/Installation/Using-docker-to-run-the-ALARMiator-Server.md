## install Docker
install docker as discriped here --> https://docs.docker.com/get-docker/

## build a docker image
execute ```docker build --file ./alarmiatorserver.dockerfile --tag alarmiatorserver:demo .``` in the root-directory of ALARMIATOR-Server
- the created image is based on ubuntu latest
- for more details please have a look at the alarmiatorserver.dockerfile where the image is build from.

## bind ports of the docker-container to ports of the local machine

By default the ALARMiator-Server whcih is now running in the docker-container is not reachable from the outside.
To get the Server reachable it is necessary to bind the ports to ports of your localhost.

This can be don with the ```-p <port at localhost>:<port in docker-container>``` at ```docker run```
The following ports are needed:
* Webinterface: ```-p 5001:5000```
* API: ```-p 5010:5010```
* socket.io: ```-p 5555:5555```
* API-HTTPS: ```-p 5443:5443```
* Wallboard: ```-p 5020:5020```
* Wallboard: ```-p 40510:40510```


## run a container
execute ```docker run --name alarmiator-server-demo -p 5001:5000 -p 40510:40510 -p 5443:5443 -p 5020:5020 -d alarmiatorserver:demo``` for testing

If you want to run ALARMiator-Server permanently use the following command:
```docker run --name alarmiator-server -p 5001:5000 -p 5010:5010 -p 40510:40510 -p 5443:5443 -p 5020:5020 -d --restart always alarmiatorserver:demo```

The ALARMiator-Server is now reachable at http://localhost:5555

## Use volume to save the database outside the docker container to keep the data persistent

in generel all data is inside the docker-container. That means if you restart the container all your data is lost.
To avoid that it is possble to use the -v parameter (https://docs.docker.com/storage/volumes/) in the docker run call.

This can be don with the ```-v <path on localhost>:<path in docker-container>``` at ```docker run```
* Database: ```-v /git/ALARMiator-Server/store:/alarmiatorserver/store```
* public: ```-v /git/ALARMiator-Server/public/assets/img:/alarmiatorserver/public/assets/img```

here a example how to use that for your alarmiator-server container:
```docker run --name alarmiator-server -p 5001:5000 -p 5010:5010 -p 40510:40510 -p 5443:5443 -p 5020:5020 -v /git/ALARMiator-Server/store:/alarmiatorserver/store -v /git/ALARMiator-Server/public/assets/img:/alarmiatorserver/public/assets/img -d --restart always alarmiatorserver:demo```

For a development-environment it is recomented to use ```-v /git/ALARMiator-Server:/alarmiatorserver```
because of the docker-container is starting the server with PM2 this has the advantage that on any code-change the server will restart automatically.

here a example how to use that for your alarmiator-server container in development:
```docker run --name alarmiator-server -p 5001:5000 -p 5010:5010 -p 40510:40510 -p 5443:5443 -p 5020:5020 -v /git/ALARMiator-Server:/alarmiatorserver -d --restart always alarmiatorserver:demo```
