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
docker-compose up --build 
docker start -a [container id || container name] // contatiner already created
docker exec -it [container id || container name] bash

// container
python script/test.py

// terminal
docker stop [container id || container name] 
```

## Useful docker command 

- build, run options

```
docker build -t #{docker id}/#{project name}:#{version} . // set image name
docker run --name hoge -it hogehoge:latest // set container name
docker run -v #{host directory}:#{container directory} -it hogehoge:latest // use local file
```

- commit (create image from container)

```
docker commit -c #{new order} [container] #{docker id}/#{project name}:#{version}
```

- remove containers or images

```
// remove stopped container, not tags images, not uses volume and networks
docker system prune

// remove stopped containers
docker container prune 

// remove stopped images
docker image prune

// remove the container or image
docker rm [container id]
docker rmi [image id]
```

## Referrence

- [Dockerでデータ分析環境を手軽に作る方法](https://amalog.hateblo.jp/entry/data-analysis-docker)
- [docker run options](https://qiita.com/shimo_yama/items/d0c42394689132fcb4b6)
- [Docker and kubernetes: The complete Guide (Udemy)](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/11436676?start=45#overview)

