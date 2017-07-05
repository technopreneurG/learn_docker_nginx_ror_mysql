Docker Compose with Nginx, Ruby on Rails and MySQL
===

* Build services:

   To build the services defined in the docker-compose file, it will build local docker images as defined in the respective Dockerfile
```bash
docker-compose -f docker-compose-build.yml build
```

* List docker images:

   List the docker images used by the containers
```bash
docker-compose -f docker-compose-build.yml images
```
   OR to list all the docker images on your system, use:
```bash
docker images
```

* Start containers:

   Build, start, and attach to containers for a service. 
```bash
docker-compose -f docker-compose-run.yml up
```
   Use -d option to run containers in detached mode.
```bash
docker-compose -f docker-compose-run.yml up -d
```

* Debugging & Troubleshooting
   Display container resource usage stats
```bash
docker stats
```

   Display the last 10 lines of logs from all containers, and follow the output
```bash
docker-compose -f docker-compose-run.yml logs --tail 10 -f
```

   Display the last 10 lines of logs from RoR app, and follow the output
```bash
docker-compose -f docker-compose-run.yml logs --tail 10 -f app
```

* [optional] Re-create the RoR application files
   To start from scratch remove everything in rorapp folder except the Dockerfile. Then run:
```bash
docker-compose -f docker-compose-build.yml run web rails new . --force --database=mysql
```

