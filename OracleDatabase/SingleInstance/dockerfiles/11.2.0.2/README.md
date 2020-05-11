# Modifications

A very simple modification to make the generated image contain a prebuilt configured database.

This makes the startup (substantially) faster, and a better candidate to be used in automated integration tests.

# Example commands

## Build image

```shell script
$ docker build . -t oracledb:11c-xe --shm-size=1G -f Dockerfile.xe
```

## Run image

```shell script
$ docker run --rm -ti -p 1521:1521 --shm-size="1g" oracledb:11c-xe
``` 