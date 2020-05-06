# python-ml-env-docker

I create environment for machine learning (xgboost, lightgbm) with docker. 

## Feature Perspective

- connect to AWS, Mysql, kubernetes

## how to activate python environment

1. build images or restart container
2. excecute container and show console of docker
3. execute python script

```
// terminal
docker-compose up --build or docker start -a [container id || container name]
docker exec -it [container id || container name] bash

// container
python script/test.py
```

## Referrence

- [Dockerでデータ分析環境を手軽に作る方法](https://amalog.hateblo.jp/entry/data-analysis-docker)
