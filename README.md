
# Test locally
- in compose mode:
```
docker-compose -f docker-stacks/docker-compose.yml -f docker-stacks/docker-compose.local.yml up
```

- in swarm mode:
```
docker-compose -f docker-stacks/docker-compose.yml -f docker-stacks/docker-compose.local.yml config | docker stack deploy --compose-file - jupyter
```

## Check if it works
```
docker stack ps jupyter
```

Log in: http://localhost/


# Run on full environment (swarm):
```
docker-compose -f docker-stacks/docker-compose.yml -f docker-stacks/docker-compose.prod.yml config | docker stack deploy --compose-file - jupyter
```
