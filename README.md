# python-ml-env-docker

I create environmentfor machine learning (xgboost, lingtgb) with docker. 

## Problem

- ../bin/bash commandを ymlに含めるとかできないのか?
- image名の設定
- docker hub に push/pullして使用する方法

## how to activate python environment

- execute sample (build and execute python script)

```
// terminal
docker-compose up --build  
docker exec -it [container id || container name] ../bin/bash

// container
python script/test.py
```

- execute (restart container and execute python script)

```
// terminal
docker start -a [container id || container name]
docker exec -it [container id || container name] ../bin/bash

// container
python script/test.py
```

## Referrence

- [Dockerでデータ分析環境を手軽に作る方法](https://amalog.hateblo.jp/entry/data-analysis-docker)
