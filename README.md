# Generic masterless docker container for saltstack
- Starts up a masterless container that listens to saltfiles in /srv/salt
- Mount up a saltstack config volume under /srv/salt.

## Clone
Clone repo to new directory.

## Build, run, detach
```
docker-compose up --build -d
```

## Salt first run

Run salt apply from your local machine

```
docker exec -it masterless001_app_1 salt-call --local state.apply
```

## Alter/create salt test code, re-apply changes

After making changes or additions, just repeat the same command to have salt apply them to your container.

```
docker exec -it masterless001_app_1 salt-call --local state.apply
```
