# data-analysis-env-docker

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
