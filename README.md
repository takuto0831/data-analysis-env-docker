# python-ml-env-docker

I create environmentfor machine learning (xgboost, lingtgb) with docker. 


## how to activate python environment

- execute sample (build and execute python script)

```
// terminal
docker-compose up --build  
docker exec -it [container id] ../bin/bash

// container
python script/test.py
```

- execute (restart container and execute python script)

```
// terminal
docker start -a [container id]
docker exec -it [container id] ../bin/bash

// container
python script/test.py
```

## Referrence

- [Dockerでデータ分析環境を手軽に作る方法](https://amalog.hateblo.jp/entry/data-analysis-docker)
