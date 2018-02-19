[![CircleCI](https://circleci.com/gh/etops/jupyter-datascience-notebook.svg?style=svg)](https://circleci.com/gh/etops/jupyter-datascience-notebook)

# Jupyter Notebook Data Science Stack
Forked from https://github.com/jupyter/docker-stacks/tree/master/datascience-notebook

Read more about Dockerfile: [JUPYTER.md](JUPYTER.md)

# Deployment with docker-compose

## Test locally

- in compose mode:
```
mkdir -p ssl work
docker-compose -f docker-stacks/docker-compose.yml -f docker-stacks/docker-compose.local.yml up
```

- in swarm mode:
```
mkdir -p ssl work
docker-compose -f docker-stacks/docker-compose.yml -f docker-stacks/docker-compose.local.yml config | docker stack deploy --compose-file - jupyter
```

### Check if it works
```
docker stack ps jupyter
```

Log in: http://localhost/ or https://localhost/


## Run on full environment (swarm):
```
docker-compose -f docker-stacks/docker-compose.yml -f docker-stacks/docker-compose.prod.yml config | docker stack deploy --compose-file - jupyter
```
