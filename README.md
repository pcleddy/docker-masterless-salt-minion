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

### From the local computer

Run salt apply from your local machine.

```
docker exec -it dockermasterlesssaltminion_app_1 salt-call --local state.apply
```

This typically takes a while.

### Or from within the container

Or run salt apply within the container.

```
docker exec -it dockermasterlesssaltminion_app_1 bash
```

Now, you should be logged in to the container. Make sure your command prompt looks different from your local machine, and, if so, run the following.

```
salt-call --local state.apply
```


## Alter/create salt test code, re-apply changes

After making changes or additions, just repeat the same command to have salt apply them to your container.

```
docker exec -it dockermasterlesssaltminion_app_1 salt-call --local state.apply
```
