# Running Single Node WordPress Example


## Pre-requisite:

## Tested Infrastructure

<table class="tg">
  <tr>
    <th class="tg-yw4l"><b>Platform</b></th>
    <th class="tg-yw4l"><b>Number of Instance</b></th>
    <th class="tg-yw4l"><b>Reading Time</b></th>
    
  </tr>
  <tr>
    <td class="tg-yw4l"><b> Play with Docker</b></td>
    <td class="tg-yw4l"><b>1</b></td>
    <td class="tg-yw4l"><b>5 min</b></td>
    
  </tr>
  
</table>

## Pre-requisite

- Create an account with [DockerHub](https://hub.docker.com)
- Open [PWD](https://labs.play-with-docker.com/) Platform on your browser 
- Click on **Add New Instance** on the left side of the screen to bring up Alpine OS instance on the right side

# Assignment
- Create a docker-compose.yml file
- Bringup the containers
- Stop the container of a single service
- Starting the stopped container

### Create a docker-compose.yml file

```
git clone https://github.com/collabnix/dockerlabs
cd dockerlabs/intermediate/workshop/DockerCompose/
cd wordpress
```


### Bringup the containers
```
$ docker-compose up -d
```

### Checking container status
```
$  docker-compose ps
 Name               Command             State                    Ports                  
----------------------------------------------------------------------------------------
Mysqldb   docker-entrypoint.sh mysqld   Up      0.0.0.0:3306->3306/tcp, 33060/tcp       
Nginx     nginx -g daemon off;          Up      0.0.0.0:443->443/tcp, 0.0.0.0:80->80/tcp
```

### Listout the services
```
$  docker-compose ps --services
webserver
dbserver
```

### Stop the container of a single service
```
$  docker-compose stop webserver
Stopping Nginx ... done
```
#### Checking container status
```
$  docker-compose ps
 Name               Command             State                  Ports              
----------------------------------------------------------------------------------
Mysqldb   docker-entrypoint.sh mysqld   Up       0.0.0.0:3306->3306/tcp, 33060/tcp
Nginx     nginx -g daemon off;          Exit 0                               
```

### Starting the stopped container
```
$  docker-compose start webserver
Starting webserver ... done
```

<b>NOTE:</b> You cant directly bringup/Start containers using `docker-compose start`.


## Contributor
[Savio Mathew](https://www.linkedin.com/in/saviovettoor)

Next >> [Lab #12: Restart Command](http://dockerlabs.collabnix.com/intermediate/workshop/DockerCompose/restart_command.html)
