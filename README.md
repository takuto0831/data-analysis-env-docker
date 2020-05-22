
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
## how to activate mysql database

1. build images
2. open command prompt
3. open mysql and sql command
4. reset db and remove container (better not to do?)

```
// terminal
docker-compose up --build
docker exec -it mysql-host bash

// mysql (container)
mysql -u [MYSQL_ROOT_PASSWORD] -p
show database;
use [table name];

//  terminal (reset db and remove container)
docker-compose down
```

## useful docker command 

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

## useful git command

- remove local changes

```
git checkout .
```

- remove all file (back to commit)

```
git clean -df .
```

- reset command

git add: working tree -> index
git commit: index -> local repository
git push: local repository -> remote repository

```
// reset latest commit
git reset --soft HEAD^

// reset latest commit, add, working tree
git reset --hard HEAD^

// reset all commit changes
git reset --hard HEAD

// reset all add changes
git reset --mixed HEAD

// remove reset
git reset --hard ORIG_HEAD
```

## Directory 

```
├── Dockerfile
├── README.md
├── docker-compose.yml
├── mysql
│   ├── Dockerfile
│   ├── db
│   │   └── init.sql
│   └── my.cnf
└── script
    └── test.py
```

## Referrence

- Udemy:
    - [ ] [Docker and kubernetes: The complete Guide (Udemy)](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/11436676?start=45#overview)

- Docker:
    - [ ] [Dockerでデータ分析環境を手軽に作る方法](https://amalog.hateblo.jp/entry/data-analysis-docker)
    - [x] [docker run options](https://qiita.com/shimo_yama/items/d0c42394689132fcb4b6)
    - [ ] [効率的に安全なDocker fileを作成する](https://qiita.com/pottava/items/452bf80e334bc1fee69a)
- Kubernetes:
    
    - [ ] [Kubernetestとは何か](https://www.sbbit.jp/article/cont1/35564#head1)
    - [ ] [数時間で完全理解 ハンズオン](https://qiita.com/Kta-M/items/ce475c0063d3d3f36d5d)
    - [ ] [Kubernetesを用いてGoogle Container Engineでコンテナクラスタをデプロイ](https://qiita.com/yusukixs/items/11601607c629295d31a7)

