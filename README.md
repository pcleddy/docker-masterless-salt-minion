# Generic masterless docker container for SaltStack

- Starts up a masterless container.
- Mounts local directory srv/salt to container's /srv/salt. Local changes are reflected within the container instantly.
- Running salt apply locally via 'docker exec' -- see below -- implements changes in the container.
- Or ssh into the container and run salt apply there.

## Clone

Clone repo to new directory.


## Build, run, detach

```
docker-compose up --build -d
```


## Salt first run

Run salt apply from your local machine.

```
docker exec -it masterless001_app_1 salt-call --local state.apply
```

This typically takes a while.


## Alter/create salt test code, re-apply changes

After making changes or additions, just repeat the same command to have salt apply them to your container.

```
docker exec -it masterless001_app_1 salt-call --local state.apply
```
