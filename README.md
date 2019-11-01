## OpenDock Template

The empty structure contains necessary folder and files to start building site based on project [opendocks/o-dock](https://github.com/opendocks/o-dock).

### How to use for project
- Clone this repository using command
```bash
    git clone git@github.com:opendocks/o-template.git
```

- Clone [opendocks/o-dock](https://github.com/opendocks/o-dock) repository within root of this repo using command
```bash
    git clone git@github.com:opendocks/o-dock.git
```

- Update general .env variables
   1. APP_BASE_DIR
   2. COMPOSE_PROJECT_NAME
   3. DOCKER_HOST_IP (IP of host machine)
   4. PHP_IDE_CONFIG
   5. PHP_VERSION (Use any value from 7.3, 7.2, 7.1, 7.0, 5.6)

- Update .env variables for Apache Service
   1. APACHE_VIRTUAL_HOST 
   
   If you are using [opendocks/o-proxy](https://github.com/opendocks/o-proxy), this will add reverse proxy automatically, though you have to manually add host entries in OS host file.
   
   If you need to add multiple host, provide comma separated values.
   
   For more details Check [opendocks/o-proxy](https://github.com/opendocks/o-proxy)
      
- Update .env variables for PHP Service
   1. Enable or disable required PHP extentions for PHP service
   2. Enable or disable required PHP extentions for Workspace service

- Update .env for MySQL Service
   1. MYSQL_VERSION
   2. MYSQL_DATABASE
   3. MYSQL_USER
   4. MYSQL_PASSWORD
   5. MYSQL_ROOT_PASSWORD  

- Search and update <b>proj.name</b> to your project name, in o-dock directory, use same as value of <b>COMPOSE_PROJECT_NAME</b> 

- Copy your code in code folder within the root directory of repository

- Create data directory in the root of this folder, it will server of MySQL data as docker volume



### Useful Commands

Docker compose useful commands
   
To build/start all services
```bash
docker-compose up
```
  
To build/start first time
```bash
docker-compose up apache php-fpm mysql
```

To build/rebuild explicitly
```bash
docker-compose up --build apache 
```

Close all running Containers
```bash
docker-compose stop
```

To stop single container do:
```bash
docker-compose stop {container-name}
```

To stop and remove all containers:
```bash
docker-compose down
```

To stop and remove single containers:
```bash
docker-compose down {container-name}
```

To enter container terminal window
```bash
docker exec -it {container-name} bash
```


### Workspace Commands
To Update all NPM packages in package.jon, (if npm-check-update is installed)
```bash
ncu -u
```