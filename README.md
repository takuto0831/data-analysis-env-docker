# python-ml-env-docker

I create environment for machine learning (xgboost, lightgbm) with docker. 

## Feature Perspective

- connect to AWS, Mysql, kubernetes

## how to activate python environment

1. build images or restart container
2. excecute container and show bash script of docker
3. execute python script

```
// terminal
docker-compose up --build or docker start -a [container id || container name]
docker exec -it [container id || container name] bash

// container
python script/test.py

// terminal
docker stop [container id || container name] 
```

## Useful docker command 

- build, run

```
docker build -t redis:latest . // set image name
docker run --name redis-server -it redis:latest // set container name
```
- remove containers or images

```
// remove stopped container, not tags images, not uses volume and networks
docker system prune

// remove stopped container
docker container prune

// remove stopped image
docker image prune
```

## Referrence

- [Dockerでデータ分析環境を手軽に作る方法](https://amalog.hateblo.jp/entry/data-analysis-docker)
- [Docker and kubernetes: The complete Guide](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/11436676?start=45#overview)

