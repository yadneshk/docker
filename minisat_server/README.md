# Minisat in Container!!

This dockerfile will containerize Minisat server which is webapp to provision and manage virtual machines and Docker containers

## Build Docker image

```sh
$ docker build -t minisat:minisat . 
```

## Run the image

```sh
$ docker container run -it -p 8000:8000 minisat:minisat 0.0.0.0:8000 
```
> This dockefile is to be stored in the same directory as Minisat server and not inside the Minisat directory

> Get Minisat repo from https://github.com/miniSat/Minisat.git
